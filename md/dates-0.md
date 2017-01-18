```python
def test_view_tickets_for_past_events(self):
    event_past = test_helpers.save_event()
    test_helpers.allocate_ticket(event_past)
    event_past.start = timezone.now() - timedelta(days=3)
    event_past.end = timezone.now() - timedelta(days=2)
    event_past.save()

    event_upcoming = test_helpers.save_event()
    test_helpers.allocate_ticket(event_upcoming)

    response = self.call_api('/tickets/past')

    self.assertEqual(len(response.data), 1)
    self.assertEqual(response.data[0]['event'], event_past)
```
