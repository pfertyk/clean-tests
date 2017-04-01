```python
def test_cannot_create_transaction_without_amount(self):
    transaction_data = {
        'organization': 'Wayne Industries',
    }

    response = self.create_transaction(transaction_data)

    self.assertEqual(response.status_code, HTTP_422)
    self.assertEqual(
        response.data['message'],
        'You need to specify the amount.'
    )
```
