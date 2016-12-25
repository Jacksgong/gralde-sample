# GRADLE SAMPLE

Some demonstrate for using gradle.

## I. Publish Multiple Modules

> In this demonstrate we just want to publish two module to the Nexus.

The final architecutre in maven Nexus would be as follows:

<img src="https://github.com/Jacksgong/gralde-sample/raw/master/art/gradle-multiple-modules.png" width="480">

### 1. Flat AAR

> This way is through the [adwiv/android-flat-aar](https://github.com/adwiv/android-fat-aar).

The demonstrate is in the [sample-flat-aar](todo-path), as you can see, in this way our local project can split two modules: 'api' and 'impl' and 'impl' module dependent 'api' module, when we publish 'impl' to the Nexus, the flat-aar script will assemble all stuff in the 'api' into the 'impl' aar directly.

### 2. Official Way

> This way is through the [35.2.5. Publishing multiple modules](https://docs.gradle.org/current/userguide/publishing_maven.html#sec:publishing_multiple_modules_to_maven).

The demonstrate is in the [sample-official-way](todo-path), in this way, our local project just has one module: 'library', but when we publish it to the Nexus, we can split it to two part: 'api' and 'impl'.


## LICENSE

```
© 2016, Jacksgong(blog.dreamtobe.cn). Licensed under the Creative Commons Attribution-NonCommercial 3.0 license (This license lets others remix, tweak, and build upon a work non-commercially, and although their new works must also acknowledge the original author and be non-commercial, they don’t have to license their derivative works on the same terms). http://creativecommons.org/licenses/by-nc/3.0/
```
