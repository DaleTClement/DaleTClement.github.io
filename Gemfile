source "https://rubygems.org"
# Jekyll 4.x is required for Ruby 4.0 compatibility (Jekyll 3.9 / github-pages
# gem uses Liquid 4.0 which calls `tainted?`, removed in Ruby 4.0).
# For GitHub Pages deployment, use a GitHub Actions workflow with Jekyll 4.x.
gem "jekyll", "~> 4.3"

# This is the default theme for new Jekyll sites.
gem "minima", "~> 2.5"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag"
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` gem to `v0.6.x` on JRuby builds since newer versions of the gem
# do not have a Java counterpart.
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

gem "csv", "~> 3.3"

gem "bigdecimal", "~> 4.0"

gem "webrick", "~> 1.7"
