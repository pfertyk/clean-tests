```python
from freezegun import freeze_time

def test_view_tickets_for_past_events(self):
    with freeze_time(2000):
        event_past = test_helpers.save_event()
        test_helpers.allocate_ticket(event_past)
    with freeze_time(3000):
        event_upcoming = test_helpers.save_event()
        test_helpers.allocate_ticket(event_upcoming)
    with freeze_time(2500):
        response = self.call_api('/tickets/past')

    self.assertEqual(len(response.data), 1)
    self.assertEqual(response.data[0]['event'], event_past)
```
