```python
def test_view_sellers_for_past_transactions(self):
    past_transaction = helpers.create_transaction()
    helpers.add_seller(past_transaction)
    # we cannot add sellers for past transactions
    past_transaction.date = tz.now() - timedelta(days=3)
    past_transaction.save()
    upcoming_transaction = helpers.create_transaction()
    helpers.add_seller(upcoming_transaction)

    response = self.call_api('/sellers/past')

    self.assertEqual(len(response.data), 1)
    self.assertEqual(
        response.data[0]['transaction'], past_transaction)
```
