```python
def test_new_transactions_are_shown_on_list(self):
    self.login_as(self.user)
    self.create_transaction()

    response = self.get_transactions()

    self.assertEqual(response.status_code, HTTP_200)
    self.assertEqual(len(response.data), 1)
```
