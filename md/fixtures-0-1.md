```python
def test_cannot_sell_stock_twice_in_one_transaction(self):
    seller = test_helpers.create_seller()
    stocks = [
        Stock(stock_id=35, no_of_shares=45, comment='First'),
        Stock(stock_id=35, no_of_shares=34, comment='Second')
    ]

    response = self.sell_stocks(seller, stocks)

    self.assertEqual(response.status_code, HTTP_422)
```
