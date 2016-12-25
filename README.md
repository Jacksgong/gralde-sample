# GRADLE SAMPLE

Some demonstrate for using gradle.

## I. Publish Multiple Modules

> In this demonstrate we just want to publish two module(A contains B) to the Nexus.

### 1. Flat AAR

> This way is through the [adwiv/android-flat-aar](https://github.com/adwiv/android-fat-aar).

The final architecutre in maven Nexus would be as follows:

<img src="https://github.com/Jacksgong/gralde-sample/raw/master/art/flat-aar-sample.png" width="320">

The demonstrate is in the [sample-flat-aar][sample-flat-aar-folder-folder], as you can see, in this way our local project can split two modules: 'api' and 'impl' and 'impl' module dependent 'api' module, when we publish 'impl' to the Nexus, the flat-aar script will assemble all stuff in the 'api' into the 'impl' aar directly.

#### Sample Checkout

- **Build 'api'**: On the 'api/' folder and execute `gradle clean build publishToMavenLocal`, then checkout the result stuff on the `~/.m2/repository/cn/dreamtobe/flataar/sample/flataar-sample-api`.
- **Build 'impl'**: On the 'impl/' folder and execute `gradle publishToMavenLocal`, then checkout the result stuff on the `~/.m2/repository/cn/dreamtobe/flataar/sample/flataar-sample-impl`.

#### Attention

In this sample we decalre all common variable params in the project [gradle.properties](https://github.com/Jacksgong/gralde-sample/blob/master/sample-flat-aar/gradle.properties). and declare the each module special `artifact id` in the `build.gradle` of each module.

#### Script File

- [publish-flat-aar.gradle][publish-flat-aar-gradle]: The gradle script for publish `impl` module.
- [publish-api.gradle][publish-api-gradle]: The gradle script for publish `api` module.
- [gralde.properties][flat-aar-gralde-properties]: All common variable params.

### 2. Official Way

> This way is through the [35.2.5. Publishing multiple modules](https://docs.gradle.org/current/userguide/publishing_maven.html#sec:publishing_multiple_modules_to_maven).

The demonstrate is in the [sample-official-way][sample-split-aar-folder-folder], in this way, our local project just has one module: 'library', but when we publish it to the Nexus, we can split it to two part: 'api' and 'impl'.

#### Sample Checkout

Just execute `gradle clean build publishToMavenLocal`. Check out result stuff on the following folders:

- `~/.m2/repository/cn/dreamtobe/splitaar/sample/splitaar-sample-api`
- `~/.m2/repository/cn/dreamtobe/splitaar/sample/splitaar-sample-impl`

#### Script File

- [publish.gralde][publish-gralde]: The gradle script for publish `library` module to `impl` and `api`.
- [gradle.properties][split-aar-gradle-properties]: All common variable params.

---

## LICENSE

```
© 2016, Jacksgong(blog.dreamtobe.cn). Licensed under the Creative Commons Attribution-NonCommercial 3.0 license (This license lets others remix, tweak, and build upon a work non-commercially, and although their new works must also acknowledge the original author and be non-commercial, they don’t have to license their derivative works on the same terms). http://creativecommons.org/licenses/by-nc/3.0/
```

[sample-flat-aar-folder-folder]: https://github.com/Jacksgong/gralde-sample/tree/master/sample-flat-aar
[sample-split-aar-folder-folder]: https://github.com/Jacksgong/gralde-sample/tree/master/sample-split-aar
[publish-flat-aar-gradle]: https://github.com/Jacksgong/gralde-sample/blob/master/sample-flat-aar/publish-flat-aar.gradle
[publish-api-gradle]: https://github.com/Jacksgong/gralde-sample/blob/master/sample-flat-aar/publish-api.gradle
[flat-aar-gralde-properties]: https://github.com/Jacksgong/gralde-sample/blob/master/sample-flat-aar/gradle.properties
[publish-gralde]: https://github.com/Jacksgong/gralde-sample/blob/master/sample-split-aar/publish.gradle
[split-aar-gradle-properties]: https://github.com/Jacksgong/gralde-sample/blob/master/sample-split-aar/gradle.properties
