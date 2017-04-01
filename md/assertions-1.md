```python
def test_transaction_list_requires_authentication(self):
    response = self.get_transactions()

    self.assertEqual(response.status_code, HTTP_401)
```
