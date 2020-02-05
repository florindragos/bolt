# frozen_string_literal: true

source ENV['GEM_SOURCE'] || 'http://ec2-52-55-30-243.compute-1.amazonaws.com:9292/'

# Disable analytics when running in development
ENV['BOLT_DISABLE_ANALYTICS'] = 'true'

gemspec

# Bolt server gems are managed here not in the gemspec
gem "hocon", '>= 1.2.5'
gem "json-schema", '>= 2.8.0'
gem "puma", '>= 3.12.0'
gem "rack", '>= 2.0.5'
gem "rails-auth", '>= 2.1.4'
gem "sinatra", '>= 2.0.4'

group(:test) do
  gem "beaker-hostgenerator"
  gem "mocha", '~> 1.4.0'
  gem "rack-test", '~> 1.0'
  gem "rubocop", '~> 0.61', require: false
end

group(:packaging) do
  gem 'packaging', '~> 0.99.35'
end

local_gemfile = File.join(__dir__, 'Gemfile.local')
if File.exist? local_gemfile
  eval_gemfile local_gemfile
end
