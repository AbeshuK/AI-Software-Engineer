# EXPLANATION.md

## What was the bug?

The bug occurred in `app/http_client.py` when `Client.oauth2_token` was a dictionary. In this case, the `request` method did not convert the dictionary to an `OAuth2Token` instance. As a result, the Authorization header was never set, causing the test `test_api_request_refreshes_when_token_is_dict` to fail.

## Why did it happen?

The code only checked if `self.oauth2_token` was an `OAuth2Token` before setting the Authorization header. Dictionaries were ignored, so the `as_header()` method could not be called, leaving the header missing.

## Why does your fix solve it?

The fix converts the dictionary to an `OAuth2Token` instance at the start of the API request:

```python
if isinstance(self.oauth2_token, dict):
    self.oauth2_token = OAuth2Token(**self.oauth2_token)