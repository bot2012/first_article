source "https://rubygems.org"

# Add missing gems for Ruby 3.4+
gem "base64"
gem "csv"
gem "logger"

# Jekyll
gem "jekyll", "~> 4.3.0"

# Default theme
gem "minima", "~> 2.0"

# Plugins
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end

# Windows support
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1.0", :install_if => Gem.win_platform?
gem "kramdown-parser-gfm"
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]