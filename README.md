This is a simple static file web application to display GOV.UK Pay service level
indicators (SLI).

Each SLI loads an iframe provided by Splunk’s embedded report feature. Basic auth
is provided via the `Staticfile.auth` however there is nothing here which we
consider secret, merely some indication of our platform's performance.

## Updating a report

Each SLI is based on a report from Splunk and makes use of the [embedded scheduled
reports](https://docs.splunk.com/Documentation/Splunk/latest/Report/Embedscheduledreports)
feature. To update, replace or add a new report follow the instructions in the
link above and copy the iframe code into `index.html`.


## Deployment

The application is designed to deploy to Cloud Foundry using the staticfile
buildpack. Log into the required domain, org and space then use the following
command to deploy:

```
cf push
```

## Developing locally

Make your life easy by using [BrowserSync](https://www.browsersync.io/)

Install globally and run with

```
❯ npm install -g browser-sync
❯ browser-sync start --server --files "**/*.html"
```

Or if you think you wont do this often just execute with

```
❯ npx browser-sync start --server --files "**/*.html"
```

BrowserSync starts a mini server to serve the project and watches for any changes and reloads automatically.
