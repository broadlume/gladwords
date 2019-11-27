# frozen_string_literal: true

require 'rake'
require 'bundler/gem_tasks'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'

RSpec::Core::RakeTask.new(:spec)
RuboCop::RakeTask.new(:lint)

task :default do
  sh "curl -fLSs https://circle.ci/cli | DESTDIR=#{__dir__}/tmp bash" unless File.exist?('./tmp/circleci')

  sh './tmp/circleci local execute build'
end
