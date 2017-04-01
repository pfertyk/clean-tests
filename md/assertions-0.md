```python
def test_list_transactions(self):
    response = self.get_transactions()
    self.assertIn(response.status_code, [HTTP_401, HTTP_403])
    self.login_as(self.user)
    response = self.get_transactions()
    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(response.data, [])
    self.create_transaction()
    response = self.get_transactions()
    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(len(response.data), 1)
```
