```python
def test_ticket_list_is_initially_empty(self):
    self.login_as(self.user)

    response = self.get_tickets()

    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(response.data, [])
```
