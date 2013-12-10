# encoding: UTF-8

require 'bundler'
Bundler::GemHelper.install_tasks

require 'rake'
require 'rake/testtask'

task :default => [:test]

desc "Run unit tests."
task :test do
  ruby "test/regex_test.rb"
end

Rake::Task["release"].clear
desc "Release a gem to gemfury"
task :release => [:clean, :build] do
  version = File.read('VERSION')
  pkg_name = "moxie-fix_microsoft_links-#{version}.gem"
  puts `fury push pkg/#{pkg_name}`
end
