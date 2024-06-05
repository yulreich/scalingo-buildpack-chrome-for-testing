# Scalingo Selenium Buildpack

This buildpack installs **Google Chrome browser** `chrome` & [`chromedriver`](https://chromedriver.chromium.org/), the Selenium driver for Chrome, in a Scalingo app.
Credits to: https://github.com/heroku/heroku-buildpack-chrome-for-testing

## Setup

You can create a multi-buildpack by creating a `.buildpacks` file at the root directory and including the link to this repository there, along with the
buildpack you are currently using. If you are using python, for example, here would be the file contents:

```
https://github.com/Scalingo/python-buildpack
https://github.com/TheDumbfounds/scalingo-buildpack-chrome-for-testing
```

## Specify your chrome and chromedriver paths

```
chrome_options = Options()
chrome_options.binary_location = "/app/.chrome-for-testing/chrome-linux64/chrome"
service = Service(
    executable_path="/app/.chrome-for-testing/chromedriver-linux64/chromedriver"
)
driver = webdriver.Chrome(service=service, options=chrome_options)
```

If you keep the default settings and run on scalingo-22, this should work as-is.

Best of luck!
