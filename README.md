# Bootstrap vagrant project for Node.js / MongoDB apps

This repo is a bootstrap vagrant-based project using Node.js and MongoDB. 

By default, it uses the precise64 vagrant base box. To start your project, complete the following steps:

*Download and install vagrant, if you haven't already (http://vagrantup.com/)*
Also make sure to install librarian

    gem install librarian
    vagrant box add base http://files.vagrantup.com/precise64.box
    git clone https://github.com/lvnilesh/nodemongoplayground.git
    cd nodemongoplayground
    librarian-chef install
    vagrant up

Wait a few moments while your VM is powered on and configured. Now you can access your VM using

    vagrant ssh
    cd app
    node app

Now you can bring up your local browser and browse to http://localhost:3000 to see your Node app in action!
