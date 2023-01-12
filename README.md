# gradle-java-fix

Gradle wrapper which takes care of the required java version (wraps `gradlew`, `gradlew.bat`, `gradle` command)

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



