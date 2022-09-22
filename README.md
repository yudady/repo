# 昌庫

## maven2

> https://repo1.maven.org/`maven2`/org/springframework/boot......


## 測試打開 maven-metadata.xml
[https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml](https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml)

## used
```xml
<repositories>
    <repository>
        <id>yudady-maven2</id>
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



## maven publish
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

## 設定
![setting](github-pages-setting.png)