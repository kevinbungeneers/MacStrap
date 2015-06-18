#!/System/Library/Frameworks/Ruby.framework/Versions/Current/usr/bin/ruby
require 'rake'


def which(cmd)
  exts = ENV['PATHEXT'] ? ENV['PATHEXT'].split(';') : ['']
  ENV['PATH'].split(File::PATH_SEPARATOR).each do |path|
    exts.each { |ext|
      exe = File.join(path, "#{cmd}#{ext}")
      return exe if File.executable?(exe) && !File.directory?(exe)
    }
  end
  return nil
end


task :default => :install

desc "Install Homebrew, Ansible and run our MacStrap playbook"
task :install => ['install:homebrew', 'install:ansible'] do
  Kernel.system('ansible-playbook macstrap.yml --ask-sudo-pass')
end

namespace 'install' do
  desc "Install Homebrew if it's not already installed"
  task :homebrew do
    if !which('brew')
      Kernel.system('ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"')
    end
  end

  desc "Install Ansible"
  task :ansible do
    Kernel.system('brew install ansible')
  end
end
