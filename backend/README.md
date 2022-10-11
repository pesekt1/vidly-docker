if process.env is not picked up when deployed in the cloud, try to use config library to read the environment variables.

config folder:
default.json:
```json
{
  "db": "mongodb://localhost/vidlyDocker"
}
```

custom-environment-variables.json:
```json
{
  "db": "MONGO_URL"
}
```
This MONGO_URL needs to be set in the cloud provider environment variables and point to our cloud mongodb instance.