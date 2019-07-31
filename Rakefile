require "bundler/gem_tasks"
require "rake/testtask"

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList["test/**/*_test.rb"]
end

task :default => [:build, :test]

require 'rake/extensiontask'
GEMSPEC = eval(File.read('fstring.gemspec'))
Rake::ExtensionTask.new('fstring', GEMSPEC) do |ext|
  ext.ext_dir = 'ext/fstring'
  ext.lib_dir = 'lib/fstring'
end
task build: :compile