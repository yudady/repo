# 倉庫
* maven
* helm-charts
* .....

## 設定
![github setting](github-pages-setting.png)

## maven
> 測試打開 maven-metadata.xml
[https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml](https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml)

> maven used
```xml
<repositories>
    <repository>
        <id>repo-maven</id>
        <url>https://yudady.github.io/repo/maven2</url>
    </repository>
</repositories>
<dependencies>
    <dependency>
        <groupId>io.github.yudady</groupId>
        <artifactId>bilibili-video</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    </dependency>
</dependencies>
```

> maven publish
```groovy

javadoc.options.encoding("utf-8")
java {
	withJavadocJar()
	withSourcesJar()
}

publishing {
	publications {
		maven2LocalRepo(MavenPublication) {
			groupId = 'io.github.yudady'
			artifactId = 'bilibili-video'
			version = '0.0.1-SNAPSHOT'

			from components.java
		}
	}

	repositories {
		maven {
			url = "file:///d:/tommy/github-repo/yudady/repo/maven2"
		}
	}
}
```

## helm-charts
* [bitnami](https://artifacthub.io/)










