if the cloud provider does not pick the process.env variable:
```js
const baseUrl = process.env.REACT_APP_API_URL || "http://localhost:3001/api";
```

...we can create 2 files:

.env.development:
```
REACT_APP_API_URL=http://localhost:3001/api
```
.env.production:
```
REACT_APP_API_URL=<DEPLOYED_BACKEND_URL/api>
```