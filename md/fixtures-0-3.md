```python
def test_cannot_allocate_overlapping_seats(self):
    seller = self.create_ticket_seller()
    seat_ranges = [Range(1, 2), Range(2, 3)]

    response = self.allocate_tickets(seller, seat_ranges)

    self.assertEqual(response.status_code, HTTP_400)
    self.assertEqual(response.data, {'errors': [
        {},
        {},
        {"You can't create duplicate items."},
        {},
    ]})
```
