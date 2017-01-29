# Activemodel::Subset::Validator

This is a subset validator for Rails 4. It's usually used to validate an array, though any object with an `include?` method will work.


A proc or lambda may also specified for more complex validation.

## Installation

Add this line to your application's Gemfile:

    gem 'activemodel-subset-validator'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install activemodel-subset-validator

## Usage

    class Person < ActiveRecord::Base
      validates_subset_of :fantasies,   :in => ['unicorns', 'rainbows', 'horsies']
      validates_subset_of :ages,        :in => 0..99
      validates_subset_of :animals,     :in => ['dogs', 'cats', 'frogs'], :message => "%{value} is not a subset of the list"
      validates_subset_of :ingredients, :in => lambda{ |f| f.type == 'fruit' ? ['apples', 'bananas'] : ['lettuce', 'carrots'] }
    end

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
