require 'guard'
require 'guard/guard'

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
      system('middleman build')
    end
  end
end

guard 'middlemanbuild' do
  watch('config.rb')
  watch(%r{^lib/^[^\.](.*)\.rb$})
  watch(%r{^source/.*$})
end
