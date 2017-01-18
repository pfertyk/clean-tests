```python
def test_ticket_list_requires_authentication(self):
    response = self.get_tickets()

    self.assertEqual(response.status_code, HTTP_401)
```
