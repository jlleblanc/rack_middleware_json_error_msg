## Note

This fork is a quick upgrade to get the gem working in Rails 5. This code is largely based off https://robots.thoughtbot.com/catching-json-parse-errors-with-custom-middleware, which I'm mentioning to credit these setup instructions for Rails:

```
# in config/application.rb
module YourApp
  class Application < Rails::Application
    # ...
    config.middleware.insert_before ActionDispatch::ParamsParser, "CatchJsonParseErrors"
    # ...
  end
end
```


### Rails rack middleware to catch JSON parse errors

Put this in your rails app's Gemfile:

    gem 'rack_middleware_json_error_msg'

If ActionDispatch::ParamsParser::ParseError gets thrown, it will send back a
HTTP 400 response with a JSON-format error message.
