require 'bundler/gem_tasks'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'
require 'reek/rake/task'
require 'yard'

RSpec::Core::RakeTask.new(:spec)

task default: :spec

RuboCop::RakeTask.new(:rubocop) do |task|
  task.patterns = ['lib/**/*.rb']
  # only show the files with failures
  task.formatters = ['files']
end

Reek::Rake::Task.new

task lint: [:rubocop, :reek]

YARD::Rake::YardocTask.new(:yard) do |t|
  t.stats_options = ['--list-undoc']
end
