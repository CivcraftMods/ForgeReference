#Adding dependencies to forge!

So the easiest way to do this is probably Maven... but forge uses gradle! Conveniently however we can still use maven to add our dependency so that's nice.

First add a new section to your build.gradle file for repositories. In this example we'll be adding my ForgeDeobf utility because why not

``` gradle
repositories {
  maven {
    name = "dydoisbutts"
    url = "http://dydoisbutts.info:8080/plugin/repository/everything/"
  }
}
```

Next in the lower dependencies block (not the one in the buildscript at the top, the one lower down with all the comments) add the dependency

``` gradle
  dependencies {
    compile 'com.biggestnerd.forgedeobf:ForgeDeobf:1.0' //basically just groupId:artifactId:version if you have the xml for it
  }
```

last thing is to run the command 'gradlew eclipse --refresh-dependencies' and refresh your eclipse workspace.
