# Contributing

Third-party patches are essential for keeping nativescript-facebook plugin great so we welcome all pull requests from everyone.

## Making Changes

* Fork the repository on GitHub
* Clone the repo:

        git clone git@github.com:<your-username>/nativescript-facebook.git

* Make commits of logical units.
* Make sure your commit messages are in the proper format.
* Add tests for your changes and make them pass. How to run tests you can find in [Testing section](#Testing)
* Push your changes to a topic branch in your fork of the repository.
* Submit a pull request to the **nativescript-facebook** repository.

## <a name='Testing'> Testing </a>

There are three main points in order to get nativescript-facebook e2e UI tests running locally on iOS 10 Simulator and Android api 23 Emulator. Before that if you want to take a look at the tests and make some changes find them located in `demo/e2e-tests` folder.

Note, that all commands below assume you have installed npm packages in /src and /demo folders (`$ npm i`) and you are using OS X in order to use both iOS Simulator and Android emulator.

* Install Appium. Test execution depends on [nativescript-dev-appium](https://github.com/NativeScript/nativescript-dev-appium) plugin which is added as dev dependency in `demo` app folder and first command satisfies its requirement to have appium installed.

        $ npm install -g appium@1.6.3

* Run Android emulator or/and iOS Simulator. For iOS appium will run simulator if such is not running. It is a requirement for appium that Android emulator has device name 'Android Emulator' and uses Android '6.0' version. For iOS Simulator you will need similator with device name 'iPhone 7 100' which is using iOS '10.0' version. These requirements come from the nativescript-dev-appium plugin and are still hardcoded in it, but notice that plugin itself is in development and the future plans are to become the ultimate testing tool for NativeScript plugins.

* Navigate to /src folder and execute:

        $ npm run ci.uitest.android

    or

        $ npm run ci.uitest.ios

That's it. You should have running UI tests in your Simulator/Emulator.