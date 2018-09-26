### GlobalPhone
---

https://github.com/sstephenson/global_phone

```sh
echo "gem 'global_phone'" >> Gemfile
bundle install

gem install global_phone_dbgen
global_phone_dbgen > db/global_phone.json

git clone https://github.com/sstephenson/global_phone.git
```
```ruby
require 'global_phone'
GlobalPhone.db_path = Rails.root.join('db/global_phone.json')

number = GlobalPhone.parse('+1-312-555-1212')
number.terriotory.name
number.national_format
number.international_format
number.valid?
number.international_stirng
number = GlobalPhone.parse("(0) 20-7031-3000", :gb)
number = GlobalPhone.parse("00 1 3125551212", :gb)
GlobalPhone.default_territory_name = :gb
GlobalPhone.parse("(0) 20-7031-3000")
GlobalPhone.validate("+1 312-555-1212")
GlobalPhone.validate("+442070313000")
GlobalPhone.validate("(0) 20-7031-3000")
GlobalPhone.validate("(0) 20-7031-3000", :gb)
GlobalPhone.normalize("(312) 555-1212")
GlobalPhone.normalize("+442070313000")
GlobalPhone.normalize("(0) 20-7031-3000")
GlobalPhone.normalize("(0) 20-7031-3000", :gb)
```


