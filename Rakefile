# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "bio-exominer"
  gem.homepage = "http://github.com/pjotrp/bioruby-exominer"
  gem.license = "MIT"
  gem.summary = %Q{Mine publications for gene names}
  gem.description = %Q{Parse publications for gene names in a fuzzy fashion}
  gem.email = "pjotr.public01@thebird.nl"
  gem.authors = ["Pjotr Prins"]
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

# require 'rspec/core'
# require 'rspec/core/rake_task'
# RSpec::Core::RakeTask.new(:spec) do |spec|
#   spec.pattern = FileList['spec/**/*_spec.rb']
# end

# RSpec::Core::RakeTask.new(:rcov) do |spec|
#   spec.pattern = 'spec/**/*_spec.rb'
#   spec.rcov = true
# end

require 'rake/testtask'

Rake::TestTask.new do |t|
  t.pattern = "spec/*_spec.rb"
end

require 'cucumber/rake/task'
Cucumber::Rake::Task.new(:features)

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "bio-exominer #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
