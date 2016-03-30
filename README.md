# herewebuy.org Site
[![Build Status][travis_badge]][travis]

This is the herewebuy site, you can see the live site on http://herewebuy.org

## Dependencies

To run this project you need to have:

- Ruby 2.3.0 - You can use [RVM](http://rvm.io)
- Node - You can get Node via `$ brew install node` or on the [website](http://nodejs.org)
- grunt-cli - You can get this via `$ npm install -g grunt-cli` or the [Getting Started guide](http://gruntjs.com/getting-started)

## Setup the project

1. Install the depedencies above
1. Clone the project

      $ git clone git@github.com:ricardok/herewebuy.org.git

1. Go into the project folder

      $ cd herewebuyorg

1. Install the gem dependencies

      $ bundle install

1. Install the grunt dependencies

      $ npm install

If everything goes OK, you can now run the project!

## Running the project

1. Start the server, this will start the jekyll server, will compile your sass files and compile your javascripts.

      $ bundle exec foreman start

1. Open [http://localhost:4000](http://localhost:4000).
