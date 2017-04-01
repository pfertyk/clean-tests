```python
def test_transaction_list_is_initially_empty(self):
    self.login_as(self.user)

    response = self.get_transactions()

    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(response.data, [])
```
