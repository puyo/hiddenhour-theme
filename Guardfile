require 'guard'
require 'guard/guard'
require 'middleman'
require 'middleman/builder'
require 'fileutils'

module ::Guard
  class Middlemanbuild < Guard
    def start
      build
    end

    def run_on_change(paths)
      build
    end

    private

    def build
      #FileUtils.rm_rf('build')
      system('middleman build')
      #::Middleman::Builder.new([], 'clean' => true).invoke_all
    end
  end
end

guard 'middlemanbuild' do
  watch('config.rb')
  watch(%r{^lib/^[^\.](.*)\.rb$})
  watch(%r{^source/.*$})
end
