```python
def test_ticket_list_contains_allocated_tickets(self):
    self.login_as(self.user)
    self.allocate_ticket()

    response = self.get_tickets()

    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(len(response.data), 1)
```
