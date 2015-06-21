#!/System/Library/Frameworks/Ruby.framework/Versions/Current/usr/bin/ruby
require 'rake'

task :default => :install

desc "Install Homebrew, Ansible and run our MacStrap playbook"
task :install => ['install:homebrew', 'install:ansible'] do
  Kernel.system 'ansible-playbook macstrap.yml --ask-sudo-pass'
end

namespace 'install' do
  desc "Install Homebrew if it's not already installed"
  task :homebrew do
    if which('brew')
      Kernel.system 'ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"'
    end
    Kernel.system 'brew update'
  end

  desc "Install Ansible if it's not already installed"
  task :ansible do
    if which('ansible')
      Kernel.system 'brew install ansible'
    end
  end
end

def which(cmd)
  return Kernel.system '/usr/bin/which -s {cmd}'
end
