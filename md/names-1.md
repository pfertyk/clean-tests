```python
def test_transaction_creation_error(self):
    transaction_data = {
        'organization': 'Wayne Industries',
    }

    response = self.create_transaction(transaction_data)

    self.assertEqual(response.status_code, HTTP_422)
```
