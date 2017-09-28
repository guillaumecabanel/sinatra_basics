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
  erb :home, layout: :'layouts/application'
end
```

vvv

### Directory structure

```bash
.
├── app.rb
└── views
    ├── home.erb
    └── layouts
        └── application.erb

```

vvv

### partial

`views/home.erb`

```erb
<h1>Welcome on this awesome app!</h1>
```

vvv

### Layout

`views/layouts/application.erb`

```erb
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My app</title>
  </head>
  <body>
    <%= yield %>
  </body>
</html>
```

---

# Deployement

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
