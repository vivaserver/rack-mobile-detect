require 'rubygems'
require 'rake'
require 'rake/testtask'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "rack-mobile-detect"
    gem.summary = %Q{Rack middleware for ruby webapps to detect mobile devices.}
    gem.description = %Q{Rack::MobileDetect detects mobile devices and adds an
    X_MOBILE_DEVICE header to the request if a mobile device is detected. Specific
    devices can be targeted with custom Regexps and redirect support is available.}
    gem.email = "accounts@majortom.fastmail.us"
    gem.homepage = "http://github.com/vivaserver/rack-mobile-detect"
    gem.authors = ["Tom Alison","Cristian R. Arroyo"]
    gem.add_development_dependency("shoulda", ">= 0")
    gem.add_dependency("rack")
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :default => :test

Rake::TestTask.new do |t|
  t.libs.push "lib"
  t.test_files = FileList['test/*_spec.rb']
  t.verbose = true
end

require 'rake/task'

#Rake::RDocTask.new do |rdoc|
  #version = File.exist?('VERSION') ? File.read('VERSION') : ""
  #rdoc.rdoc_dir = 'rdoc'
  #rdoc.title = "rack-mobile-detect #{version}"
  #rdoc.rdoc_files.include('README*')
  #rdoc.rdoc_files.include('lib/**/*.rb')
#end
