# bintray

The easiest way to publish your library to bintray.

This library is based on https://github.com/nuuneoi/JCenter but modified to have configuration file. 


## Usage

### 1. Setup project local.properties

```
bintray.apikey=xxx
bintray.user=xxx
bintray.gpg.password=xxx
```

### 2. Add dependencies to project gradle

```
classpath "com.jfrog.bintray.gradle:gradle-bintray-plugin:1.2"
classpath "com.github.dcendents:android-maven-gradle-plugin:1.3"
```

### 3. Add bintray configuration to project gradle

```
ext {
  bintray = [
      bintrayRepo       : "maven",
      bintrayName       : "smooth-app-bar-layout",

      publishedGroupId  : "me.henrytao",
      libraryName       : "SmoothAppBarLayout",
      artifact          : "smooth-app-bar-layout",

      libraryDescription: "Smooth version of Google Support Design AppBarLayout",

      siteUrl           : "https://github.com/henrytao-me/smooth-app-bar-layout",
      gitUrl            : "https://github.com/henrytao-me/smooth-app-bar-layout.git",

      libraryVersion    : rootProject.ext.android.versionName,

      developerId       : "henrytao",
      developerName     : "Henry Tao",
      developerEmail    : "hi@henrytao.me",

      licenseName       : "The Apache Software License, Version 2.0",
      licenseUrl        : "http://www.apache.org/licenses/LICENSE-2.0.txt",
      allLicenses       : ["Apache-2.0"]
  ]
}
```

### 4. Apply these gradle files to library gradle

```
apply from: "https://raw.githubusercontent.com/henrytao-me/bintray/master/installv1.gradle"
apply from: "https://raw.githubusercontent.com/henrytao-me/bintray/master/bintrayv1.gradle"
```

### 5. Setup pom

```
./gradlew install
```

### 6. Deploy library

```
./gradlew bintrayUpload
```


## Thanks

- [nuuneoi](https://github.com/nuuneoi)


## License

    Copyright 2015 "Henry Tao <hi@henrytao.me>"

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.