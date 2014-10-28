[![badge: Download]][badge url: Download] [![badge: LICENSE]][LICENSE.md] [![badge: Semver 2.0.0]][badge url: Semver 2.0.0] [![badge: gratipay]][badge url: gratipay] 

# [LGIO], Gradle plugin

<!-- MarkdownTOC -->

- [Usage](#usage)
- [Changelog](#changelog)
- [Bugs / Issues / Feature requests / Contribution](#bugs--issues--feature-requests--contribution)
- [License](#license)

<!-- /MarkdownTOC -->

**[LGIO]** **(Lightweight Gradle IO)** is a plugin that solves the problem of
`System.console()` being `null` by using a GUI in those cases

## Usage

Using **[LGIO]** in your project is quite staightforward.

**Add the following to your buildscript:**
```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'se.centril.lgio:gradle-plugin-lgio:0.1.1'
    }
}

apply plugin 'lgio'
```

**Henceforth you can use it like:**
```groovy
// In some task:
lgio.println "Reading signing configuration"

def storeFile   = file( lgio.readLineReq "Keystore file, rel path" )
def keyAlias    = io.readLineReq "Key alias"
def storePw     = io.readPasswordReq "Keystore password"
def keyPw       = io.readPasswordReq "Key password"
```

A method that ends with `Req`, for example `readLineReq` does the same as `readLine` but the `Req` version throws an exception when an empty string is given by the user/client.

**Normally, `lgio` and `io` can be used interchangably, they are aliases.**

To stop **[LGIO]** from making `io` an alias, add:
```groovy
project.ext.lgioAliasDisable = true
```

## Changelog

See **[CHANGES.md]**

## Bugs / Issues / Feature requests / Contribution

Want to contribute? Great stuff! Please use the issue system that github provides to report bugs/issues or request an enhancement. Pull requests are also more than welcome.

## License

**[LGIO]** is licensed under **Apache License 2.0**, see **[LICENSE.md]** for more information.

<!-- references -->

[badge: Download]: https://api.bintray.com/packages/centril/maven/se.centril.lgio%3Agradle-plugin-lgio/images/download.svg
[badge url: Download]: https://bintray.com/centril/maven/se.centril.lgio%3Agradle-plugin-lgio/_latestVersion
[badge: Build Status]: http://img.shields.io/travis/Centril/gradle-plugin-lgio.svg
[badge url: Build Status]: https://travis-ci.org/Centril/gradle-plugin-lgio
[badge: Coverage Status]: http://img.shields.io/coveralls/Centril/gradle-plugin-lgio.svg
[badge url: Coverage Status]: https://coveralls.io/r/Centril/gradle-plugin-lgio
[badge: License]: http://img.shields.io/badge/license-ASL_2.0-blue.svg
[LICENSE.md]: LICENSE.md
[badge: Semver 2.0.0]: http://img.shields.io/badge/semver-2.0.0-blue.svg
[badge url: Semver 2.0.0]: http://semver.org/spec/v2.0.0.html
[badge: gratipay]: http://img.shields.io/gratipay/Centril.svg
[badge url: gratipay]: https://gratipay.com/Centril

[LGIO]: https://github.com/centril/gradle-plugin-lgio
[LICENSE.md]: LICENSE.md
[CHANGES.md]: CHANGES.md

<!-- references -->