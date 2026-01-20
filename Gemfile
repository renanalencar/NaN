source "https://rubygems.org"

# GitHub Pages compatible Jekyll (using latest version)
gem "github-pages", group: :jekyll_plugins

# Essential Jekyll plugins
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-sitemap", "~> 1.4"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-redirect-from", "~> 0.16"
end

# Windows platform dependencies
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", "~> 2.0"
  gem "tzinfo-data"
  # File watching alternatives for better Windows support
  gem "wdm", "~> 0.2.0"
  # Fallback file watcher
  gem "listen", "~> 3.9"
end

# Required for Jekyll 3.9+ and Ruby 3.0+
gem "webrick", "~> 1.8"

# Ruby 3.4+ standard library gems (now separate gems)
gem "csv", "~> 3.3"
gem "logger", "~> 1.6"
gem "ostruct", "~> 0.6"
gem "base64", "~> 0.3"

# Performance and compatibility
gem "kramdown-parser-gfm", "~> 1.1"

# Security updates
gem "addressable", "~> 2.8"
gem "nokogiri", "~> 1.17"
