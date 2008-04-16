require 'rubygems'
require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'
require 'rake/gempackagetask'
require 'spec/rake/spectask'

require './tasks/hoex.rb'  # Alex's patched version of Hoe

GEM_VERSION = "0.2.57"
GEM_NAME = "erector"

Hoe.new(GEM_NAME, GEM_VERSION) do |hoe|
  hoe.name = GEM_NAME
  hoe.developer("Pivotal Labs", "alex@pivotallabs.com")
  hoe.rdoc_dir = "rdoc"
  hoe.remote_rdoc_dir = "rdoc"
  hoe.files = ["{spec,lib}/**/*", "README.txt", "bin/erect"]
  hoe.extra_deps = [['treetop', ">= 1.2.3"]]
end
Hoe::remove_tasks("audit", "check_manifest", "post_blog", "multi", "test", "test_deps")

desc "Default: run tests"
task :default => :spec

task :test => :spec

desc "Run the specs for the erector plugin"
Spec::Rake::SpecTask.new do |t|
  t.spec_files = FileList['spec/**/*_spec.rb']
end
