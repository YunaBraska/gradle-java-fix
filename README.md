# gradle-java-fix

Gradle wrapper which takes care of the required java version (wraps `gradlew`, `gradlew.bat`, `gradle` command)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate/?hosted_button_id=HFHFUT3G6TZF6)

[![Issues][issues_shield]][issues_link]
[![Commit][commit_shield]][commit_link]
[![License][license_shield]][license_link]
[![Size][size_shield]][size_shield]
![Label][technology]
![Label][label_shield]

### Motivation

I always
get the stupid
error [Unsupported class file major version XX](https://mkyong.com/java/java-unsupported-class-file-major-version-61/)
even when I define `sourceCompatibility` or `targetCompatibility` in my `build.gradle` file! That's cause gradle does
not take care of the java version. This script will change that now

### Usage

* Place the `gw` sh script next to you `gradlew` file and use it like you would with `gradlew` e.g. `gw --version`

### Example

```shell
cd my_repo
ls -1
> gw
> build.gradle
> gradlew
> gradle.bat

cat build.gradle | grep sourceCompatibility
> sourceCompatibility = JavaVersion.VERSION_1_8

echo $JAVA_HOME
> /Library/Java/JavaVirtualMachines/graalvm-ce-java17-22.1.0/Contents/Home

gw --version
> ------------------------------------------------------------
> Gradle 6.8.3
> ------------------------------------------------------------
> JVM:          1.8.0_312 (Azul Systems, Inc. 25.312-b07)
```

### Features

* Auto update: the `gw` sh script will update itself as long as env is not `GW_UPDATE="false"`
* Auto Detect command `gradlew`, `gradlew.bat` or fallback to `gradle` command
* Auto Detect Java from `sourceCompatibility` or `targetCompatibility` in `build.gradle*`
* Debug mode with one of the gradle parameters: `-d` `-w` `-s` `-S`

### Current limitations

* The script is NOT tested on `windows` or `cygwin`
* `sourceCompatibility` or `targetCompatibility` is needed in `build.gradle*` but the script cant resolve variables
    * workaround: call the version variable like the java version e.g. `sourceCompatibility = JavaVersion.VERSION_1_8`
* It's not installing any java versions for you
    * Use your IDE to download the right java version

### Install to a repository

* Download the and add `gw` sh script to your repository (next to your `gradlew`)

### Install as global command / alias

* Download the `gw` sh script to your home folder (`~`)
* Add this line `alias gw=~/gw` to your bash profile or .zshrc, ...


[build_shield]: https://github.com/YunaBraska/gradle-java-fix/workflows/RELEASE/badge.svg

[build_link]: https://github.com/YunaBraska/gradle-java-fix/actions?query=workflow%3AMVN_RELEASE

[maintainable_shield]: https://img.shields.io/codeclimate/maintainability/YunaBraska/gradle-java-fix?style=flat-square

[maintainable_link]: https://codeclimate.com/github/YunaBraska/gradle-java-fix/maintainability

[coverage_shield]: https://img.shields.io/codeclimate/coverage/YunaBraska/gradle-java-fix?style=flat-square

[coverage_link]: https://codeclimate.com/github/YunaBraska/gradle-java-fix/test_coverage

[issues_shield]: https://img.shields.io/github/issues/YunaBraska/gradle-java-fix?style=flat-square

[issues_link]: https://github.com/YunaBraska/gradle-java-fix/commits/main

[commit_shield]: https://img.shields.io/github/last-commit/YunaBraska/gradle-java-fix?style=flat-square

[commit_link]: https://github.com/YunaBraska/gradle-java-fix/issues

[license_shield]: https://img.shields.io/github/license/YunaBraska/gradle-java-fix?style=flat-square

[license_link]: https://github.com/YunaBraska/gradle-java-fix/blob/main/LICENSE

[tag_shield]: https://img.shields.io/github/v/tag/YunaBraska/gradle-java-fix?style=flat-square

[tag_link]: https://github.com/YunaBraska/gradle-java-fix/releases

[size_shield]: https://img.shields.io/github/repo-size/YunaBraska/gradle-java-fix?style=flat-square

[label_shield]: https://img.shields.io/badge/Yuna-QueenInside-blueviolet?style=flat-square

[gitter_shield]: https://img.shields.io/gitter/room/YunaBraska/gradle-java-fix?style=flat-square

[gitter_link]: https://gitter.im/gradle-java-fix/Lobby

[technology]: https://img.shields.io/badge/sh-POSIX-blueviolet?style=flat-square

