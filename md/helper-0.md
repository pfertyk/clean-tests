```python
def test_allocating_tickets(self):
    self._validate_tickets()

def test_allocating_tickets_admin(self):
    tickets = self._validate_tickets(False)
    self.assertEqual(tickets, [])

def test_filter_past_tickets(self):
    self._validate_tickets()

    response = self.call_api('/tickets/past')
    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(len(response.data), 3)
```
