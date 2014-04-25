# OmniAuth Coinbase

OmniAuth 2 strategy for [Coinbase](https://coinbase.com/)

For more details, read the [Coinbase API Reference](https://coinbase.com/docs/api/overview#oauth2)

# Installation

Add to your Gemfile:

```ruby
gem "omniauth-coinbase"
```

Then bundle install.

# Usage

Here's an example, adding the middleware to a Rails app in config/initializers/omniauth.rb:

```ruby
Rails.application.config.middleware.use OmniAuth::Builder do
  provider :coinbase, ENV["COINBASE_KEY"], ENV["COINBASE_SECRET"]
end
```

You can now access the OmniAuth Coinbase OAuth2 URL: /auth/coinbase

# Configuration

You can configure permissions/scope, which you pass in to the `provider` method after your `COINBASE_KEY` and `COINBASE_SECRET`:

```ruby
Rails.application.config.middleware.use OmniAuth::Builder do
  provider :coinbase, ENV["COINBASE_KEY"], ENV["COINBASE_SECRET"], scope: 'send addresses'
end
```

The format is a space separated list of strings from Coinbase's [list of OAuth Permissions](https://coinbase.com/docs/api/authentication#permissions). If you don't include any `scope` it will default to `all`.

# License

Copyright (c) 2012 by Miguel Palhas

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
