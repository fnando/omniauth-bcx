# Omniauth::BCX

[![Travis-CI](https://travis-ci.org/fnando/omniauth-bcx.png)](https://travis-ci.org/fnando/omniauth-bcx)
[![CodeClimate](https://codeclimate.com/github/fnando/omniauth-bcx.png)](https://codeclimate.com/github/fnando/omniauth-bcx)
[![Test Coverage](https://codeclimate.com/github/fnando/omniauth-bcx/badges/coverage.svg)](https://codeclimate.com/github/fnando/omniauth-bcx/coverage)
[![Gem](https://img.shields.io/gem/v/omniauth-bcx.svg)](https://rubygems.org/gems/omniauth-bcx)
[![Gem](https://img.shields.io/gem/dt/omniauth-bcx.svg)](https://rubygems.org/gems/omniauth-bcx)

[Basecamp](http://basecamp.com)'s OAuth2 Strategy for OmniAuth.

## Installation

Add this line to your application's Gemfile:

    gem 'omniauth-bcx'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omniauth-bcx

## Usage

`OmniAuth::Strategies::Basecamp` is simply a Rack middleware. Read the OmniAuth docs for detailed instructions: <https://github.com/intridea/omniauth>.

First, create a new application at `https://launchpad.37signals.com/integrations`. Your callback URL must be something like `https://example.com/auth/basecamp/callback`. For development you can use `http://127.0.0.1:3000/auth/basecamp/callback`.

Here's a quick example, adding the middleware to a Rails app in `config/initializers/omniauth.rb`. This example assumes you're exporting your credentials as environment variables.

```ruby
Rails.application.config.middleware.use OmniAuth::Builder do
  provider :basecamp, 
            ENV['BASECAMP_CLIENT_ID'], 
            ENV['BASECAMP_CLIENT_SECRET']
end
```

Now visit `/auth/basecamp` to start authentication against Sentry.

## Contributing

1. Fork [omniauth-bcx](https://github.com/fnando/omniauth-bcx/fork)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
