###
### Docker, Angular with Tutum setup...
###
npm install -g bower
cd code/docker-backyard/
mkdir docker-angular-tutum/
cd docker-angular-tutum/
npm init
bower init
echo '{"directory": "client/bower_components"}' > .bowerrc
#--------------------------------------------------------------------------------

###
### Install Angular, Angular-UI-Router, Bootstrap and Angular-Bootstrap
###
cd code/docker-backyard/docker-angular-tutum/
clear && bower install --save angular angular-ui-router bootstrap angular-bootstrap
#--------------------------------------------------------------------------------

###
### Install Express with compression, log support (morgan) and error handling
###
cd code/docker-backyard/docker-angular-tutum/
npm install --save express compression morgan errorhandler
#--------------------------------------------------------------------------------
###
### Install Test Framework: Karma, Mocha, Chai, PhantomJS
###
cd code/docker-backyard/docker-angular-tutum/
clear && npm install --save-dev karma karma-mocha karma-chai karma-phantomjs-launcher karma-ng-html2js-preprocessor
#--------------------------------------------------------------------------------
###
### Install Cask (for installing BIN over Homebrew)
###
brew install caskroom/cask/brew-cask
#--------------------------------------------------------------------------------
###
### Create client folder structure
###
cd code/docker-backyard/docker-angular-tutum/
mkdir -p client/app
mkdir client/app/main
mkdir client/app/about
mkdir -p client/components/navbar
#-------------------------------------------------------------------------------- ###
### Create client files...
###
cd code/docker-backyard/docker-angular-tutum/
touch client/index.html
touch client/app/app.js
touch client/app/main/main.js
touch client/app/main/main.html
touch client/app/main/main-controller.js
touch client/app/about/about.js
touch client/app/about/about.html
touch client/components/navbar/navbar.html
#-------------------------------------------------------------------------------- ###
### Create server folder structure...
###
mkdir -p server/config
mkdir -p server/components/errors
mkdir -p server/views
#--------------------------------------------------------------------------------
###
### Create server files
###
cd code/docker-backyard/docker-angular-tutum/
touch server/app.js
touch server/routes.js
touch server/config/index.js
touch server/config/express.js
touch server/components/errors/index.js
touch server/views/404.html
#--------------------------------------------------------------------------------
###
### Run the server..
###
clear && node server/app.js 
#--------------------------------------------------------------------------------
#
# Run the tests
#
# Modify the package.json to specify the test script
"scripts": {
  "test": "node ./node_modules/karma/bin/karma start --single-run"
}
# Now, run the tests
npm test
#--------------------------------------------------------------------------------
