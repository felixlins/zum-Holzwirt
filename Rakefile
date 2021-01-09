require 'bundler/inline'

gemfile do
  source "https://rubygems.org"
  gem "tilt"
  gem "slim"
end

require "fileutils"
require "slim"
require "yaml"
require "slim/include"

task default: :build

task :build do
  Dir.glob(File.join(__dir__, "*.slim")).each do |file|
		html = file.ext(".html")
    puts "Building #{html}"
    File.write(html, Tilt.new(file, pretty: true).render)
  end
end

task :clean do
  Dir.glob(File.join(__dir__, "*.slim")).each do |file|
    FileUtils.rm file.ext(".html")
  end
end
