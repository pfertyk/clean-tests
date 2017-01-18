```python
def test_event_error(self):
    organization = test_helpers.create_organization()
    event_data = {
        'name': 'Iron Maiden concert',
        'organization': organization,
    }

    response = self.create_event(event_data)

    self.assertEquals(response.status_code, HTTP_400)
```
