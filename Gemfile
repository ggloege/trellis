source "https://rubygems.org"

# Vanilla Jekyll 4 + plugins. We do NOT use the github-pages gem
# because it pins very old Jekyll/Liquid versions that break on
# Ruby 3.2+. Instead, .github/workflows/pages.yml builds with this
# same Gemfile and deploys to GitHub Pages.
gem "jekyll", "~> 4.3"

group :jekyll_plugins do
  gem "jekyll-seo-tag", "~> 2.8"
end

# Stdlib gems extracted from Ruby 3.4+ defaults that some Jekyll
# dependencies still expect via require.
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"
gem "ostruct"
