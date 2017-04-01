```python
from freezegun import freeze_time

def test_view_sellers_for_past_transactions(self):
    with freeze_time('2000-01-01'):
        past_transaction = helpers.create_transaction()
        helpers.add_seller(past_transaction)
    with freeze_time('3000-01-01'):
        upcoming_transaction = helpers.create_transaction()
        helpers.add_seller(upcoming_transaction)
    with freeze_time('2500-01-01'):
        response = self.call_api('/sellers/past')
    self.assertEqual(len(response.data), 1)
    self.assertEqual(
        response.data[0]['transaction'], past_transaction)
```
