# encoding: UTF-8

require 'bundler'
Bundler::GemHelper.install_tasks

require 'rubygems'
require 'bundler/setup'
require 'rake'
require 'rake/testtask'

require 'jeweler'
Jeweler::Tasks.new do |gem| 
  gem.name = 'moxie-fix_microsoft_links'
  gem.summary = %Q{Fixes redirects to login pages when a user clicks a link to your site from a Microsoft application like Word or Excel}
  gem.description = %Q{Fixes redirects to login pages when a user clicks a link to your site from a Microsoft application like Word or Excel}
  gem.email = "jonbell@spamcop.net"
  gem.homepage = "https://github.com/moxiespaces/moxie-fix_microsoft_links"
  gem.authors = ["Zachary Kloepping", "Jon Bell"]
  gem.files.include 'lib/**/*.rb'
  gem.files.exclude '.bundle/*'
  gem.files.exclude '.rvmrc'
end
Jeweler::RubygemsDotOrgTasks.new

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
