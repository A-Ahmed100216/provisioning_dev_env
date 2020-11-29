# Provisioning with vagrant

# Core of Provisioning
* There are some actions which are core to provisioning
* These concepts are tool and language agnostic i.e not dependant on one specific tool or language  
* Making files available i.e Syncing files
* Being able to run commands/scripts
* Injecting environment variables

## Syncing Files
* Allowing us to send files and sync them into the VM.
* This is so we can make code and other necessary files available
We can use the following code in our Vagrantfile to ensure syncing with the app.
`config.vm.synced_folder"path/to/origin/folder", "path to destination"``

### Running a Bash Script
* Running a script which will run every time
This can install packages, alter files, do actions in our linux servers when we first run `vagrant up`
* This is a key aspect of provisioning
* Allows us to set the machine to a state which is desirable and automate the process
* Steps:
  * Create a file which takes bash commands i.e provision.sh file
  * Tell vagrant to run the file
  * Run the bash file as soon as vagrant is run

# New Project
When given a new Project, need to ask a few questions to get going:
### What language is it in?
* Code is in JS
* Tests in Ruby

## Is there a framework needed e.g. rails, Flask, Django, Wordpress
* No

## Any specific packages which need to be installed e.g Gemfile, requirements.txt
* With environment file, you have a Gemfile which has dependencies.
## Any tests?
* Integration tests to run outside the virtual machine, and some unit tests in JS within the virtual machine.

#### Testing
* .rspec is the ruby equivalent of pytest. rspec is ruby's testing framework. It needs to be installed.
* Gems are the packages in ruby.
* Bundler is ruby's package manager
* to install gems from the Gemfile, you run
`bundle install`

* JS package manager is npm(node package manager)
`npm packages`
   * after version 6, comes preloaded  with npm.
   * if needs be, install npm
* Ubuntu package manager is `apt-get`

#### Installing tests
1. Install Bundler
`sudo gem install bundler`
2. go to folder with Gemfile
3. run Bundler
4. Run tests
`rake spec`
