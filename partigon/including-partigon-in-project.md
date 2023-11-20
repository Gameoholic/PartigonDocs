# Including Partigon in project

To add Partigon as a Maven dependency:

```gradle
<repository>
  <id>gameoholic-repo</id>
  <url>https://repo.gameoholic.xyz/releases</url>
</repository>

<dependency>
  <groupId>xyz.gameoholic</groupId>
  <artifactId>partigon</artifactId>
  <version>version</version>
  <scope>provided</scope>
</dependency>
```

To add it as a Gradle (Kotlin) dependency:

```gradle
repositories {
    maven {
        url = uri("https://repo.gameoholic.xyz/releases")
    }
}
dependencies {
    compileOnly("xyz.gameoholic:partigon:1.1.1")
}
```

After doing this, you must include the Partigon .jar file in your plugins folder.
