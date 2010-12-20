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
  gem.name = "ruby-spreadsheet"
  gem.homepage = "http://github.com/lda/ruby-spreadsheet"
  gem.license = "GPLv3"
  gem.summary = %Q{The Spreadsheet Library is designed to read and write Spreadsheet Documents}
  gem.description = %Q{As of version 0.6.0, only Microsoft Excel compatible spreadsheets are supported}
  gem.email = "lda@openteam.ru, mhatakeyama@ywesee.com, zdavatz@ywesee.com"
  gem.authors = ["Dmitry Lihachev", "Masaomi Hatakeyama", "Zeno R.R. Davatz"]
  gem.add_runtime_dependency 'ruby-ole', '> 1.2'
  gem.executables << 'xlsopcodes'

  #  gem.add_development_dependency 'rspec', '> 1.2.3'
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "ruby-spreadsheet #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
