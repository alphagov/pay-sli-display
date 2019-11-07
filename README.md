This is a simple static file web application to display GOV.UK Pay service level
indicators (SLI).

Each SLI loads an iframe provided by Splunk's embedded report feature. Basic auth
is provided via the `Staticfile.auth` however there is nothing here which we
consider secret, merely some indication of our platform's performance.


## Deployment

The application is designed to deploy to Cloud Foundry using the staticfile
buildpack. Log into the required domain, org and space then use the following
command to deploy:

```
cf push
```

