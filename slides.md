# Sinatra basics

👉 http://www.sinatrarb.com/

---

## Hello World

```ruby
# app.rb

require 'sinatra'

get '/' do
  'Hello world!'
end

```

Launch server:
```sh
ruby app.rb
```

See your app on http://localhost:4567 🎉

---

## Views

```ruby
# app.rb

get '/' do
  erb :home
end
```

vvv

### Directory structure

```bash
.
├── app.rb
└── views
    ├── home.erb
    └── search.erb

```

---

# Deployement

<img class="full-screen" src="images/rocket.gif">

vvv

## Config Rack application

`Gemfile`

```ruby
source 'https://rubygems.org'
ruby '2.4.1'
gem 'sinatra'
```

Install gems:

```bash
bundle install
```

vvv

`config.ru`

```ruby
require './app'
run Sinatra::Application
```

run server:

```bash
bundle exec rackup -p 8080 config.ru
```

vvv

## CleverCloud

👉 https://console.clever-cloud.com

vvv

## deploy

```bash
git add config.ru Gemfile
git commit -m "ready to deploy"
git push origin master
```
