```python
def test_list_tickets(self):
    response = self.get_tickets()
    self.assertIn(response.status_code, [HTTP_401, HTTP_403])

    self.login_as(self.user)

    response = self.get_tickets()
    self.assertEqual(response.status_code, HTTP_200)

    self.assertEqual(response.data, [])

    self.allocate_ticket()

    response = self.get_tickets()
    self.assertEqual(response.status_code, HTTP_200)

    self.assertEqual(len(response.data), 1)
```
