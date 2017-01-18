```python
def test_cannot_create_event_without_venue(self):
    organization = test_helpers.create_organization()
    event_data = {
        'name': 'Iron Maiden concert',
        'organization': organization,
    }

    response = self.create_event(event_data)

    self.assertEquals(response.status_code, HTTP_422)
    self.assertEquals(
        response.data['message'],
        'You cannot create an event without a venue.'
    )
```
