require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "email2sms"
    gem.summary = "Pure Ruby e-mail to sms gateway"
    gem.description = "Free and pure Ruby E-Mail to sms gateway including an extensible filterchain to filter and manipulate incoming emails before sending them as text messages."
    gem.email = "email2sms@avarteq.de"
    gem.homepage = "http://github.com/avarteq/email2sms"
    gem.authors = ["Julian Fischer"]
    gem.bindir = "bin"
    gem.executables = ["email2smsd"]
    gem.add_dependency("developergarden_sdk", "=0.0.8")
    gem.add_dependency("daemons", "=1.0.10")
    gem.add_dependency("tmail", "=1.2.3.1")
    
    # gem.add_development_dependency 
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*_test.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/*_test.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  if File.exist?('VERSION')
    version = File.read('VERSION')
  else
    version = ""
  end

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "email2sms #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
