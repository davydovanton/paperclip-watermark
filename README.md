# PaperclipWatermark [![Dependency Status](https://gemnasium.com/vikewoods/paperclip-watermark.png)](https://gemnasium.com/vikewoods/paperclip-watermark) [![Build Status](https://travis-ci.org/vikewoods/paperclip-watermark.png)](https://travis-ci.org/vikewoods/paperclip-watermark)

Papercli Watermark processor

## Usage
Edit your paperclip model:

```ruby
# app/models/assets.rb
class Asset < ActiveRecord::Base
  attr_accessible :attachment

  # Paperclip image attachments
  has_attached_file :attachment,
    processors: [:watermark],
    styles: {
      thumb: '150x150>',
      original: {
        geometry: '800>',
        watermark_path: "#{Rails.root}/public/images/logo.png"
      }
    },
    url: '/assets/attachment/:id/:style/:basename.:extension',
    path: ':rails_root/public/assets/attachment/:id/:style/:basename.:extension',
    default_url: '/images/:style/mising.png'
end

```

## Installation
Add this line to your application's Gemfile:
```ruby
gem 'paperclip-watermark'
```

or install from github:
```ruby
gem 'paperclip-watermark', github: 'vikewoods/paperclip-watermark'
```

And then execute:

    $ bundle install

Or install it yourself as:
```ruby
gem install paperclip-watermark
```

## Contributing
1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
