# Web Python Snippets

**Write the body for each page of a specified amount of re-directs to a file**

```text
text
import requests
from urllib.parse import urlparse

url = ''
f = open("output.txt", "a")
session = requests.session()
session.max_redirects = 9999999
r = session.get('', allow_redirects=False)

for redirect in session.resolve_redirects(r, r.request):
    print(redirect.text)
```

