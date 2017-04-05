```python
def test_cannot_sell_stock_twice_in_one_transaction(self):
    seller = test_helpers.create_ticket_seller()
    stocks = [Stock(stock_id=1), Stock(stock_id=1)]

    response = self.sell_stocks(seller, stocks)

    self.assertEqual(response.status_code, HTTP_422)
```
