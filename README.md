# LibUtils
Utilities to upload libraries quickly to maven repository in Bintray.

## Steps
1. Add bintray username (`bintray.user`) and API key (`bintray.apikey`) in the `local.properties` file.
2. Add these in the top-level `build.gradle` file -  `classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.4'` and `classpath 'com.github.dcendents:android-maven-gradle-plugin:1.4.1'`
3. Add these in the library `build.gradle` file - `apply from: 'https://raw.githubusercontent.com/aritraroy/LibUtils/master/install.gradle'` and `apply from: 'https://raw.githubusercontent.com/aritraroy/LibUtils/master/upload.gradle'`
4. Add this in your library `build.gradle` file
```
ext {
    bintrayRepo = 'maven'
    bintrayName = 'bintray-project-name'

    publishedGroupId = 'com.aritraroy.lib'
    libraryName = 'library'
    artifact = 'library'

    libraryDescription = 'Description of the library'

    siteUrl = 'https://github.com/aritraroy/library'
    gitUrl = 'https://github.com/aritraroy/library.git'

    libraryVersion = '1.0.0'

    developerId = 'aritraroy'
    developerName = 'Aritra Roy'
    developerEmail = 'aritra.roy.in@gmail.com'

    licenseName = 'The Apache Software License, Version 2.0'
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'
    allLicenses = ["Apache-2.0"]
}
```
5. Gradle tasks to run - .`/gradlew install` and `./gradlew bintrayUpload`