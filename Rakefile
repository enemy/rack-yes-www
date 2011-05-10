require "bundler"
Bundler.setup

require "rspec/core/rake_task"
RSpec::Core::RakeTask.new(:spec)

gemspec = eval(File.read("rack-yes-www.gemspec"))

task :build => "#{gemspec.full_name}.gem"

file "#{gemspec.full_name}.gem" => gemspec.files + ["rack-yes-www.gemspec"] do
  system "gem build rack-yes-www.gemspec"
  system "gem install rack-yes-www-#{Rack::YesWWW::VERSION}.gem"
end
