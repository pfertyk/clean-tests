```python
def test_cannot_allocate_overlapping_seats(self):
    seller = self.create_ticket_seller(
        name='Frank', surname='Sinatra', age='33')
    seat_ranges = [
        Range(34, 84, section='Balcony', block='B1'),
        Range(56, 95, section='Balcony', block='B1'),
    ]

    response = self.allocate_tickets(seller, seat_ranges)

    self.assertEqual(response.status_code, HTTP_422)
```
