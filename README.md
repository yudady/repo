# 倉庫

* maven
* helm-charts

## 設定

![github setting](github-pages-setting.png)

## maven

> 測試打開 maven-metadata.xml
[https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml](https://yudady.github.io/repo/maven2/io/github/yudady/bilibili-video/maven-metadata.xml)

## maven used

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
        <artifactId>tools-spring-web</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    </dependency>
    
    <dependency>
        <groupId>io.github.yudady</groupId>
        <artifactId>tools-utils</artifactId>
        <version>0.0.2-SNAPSHOT</version>
    </dependency>

</dependencies>
```

## gradle used

```groovy

repositories {
	mavenCentral()
	maven {
		url = uri("https://yudady.github.io/repo/maven2")
	}
	maven {
		url = uri("https://maven.pkg.github.com/yudady/io.github.yudady")
		credentials {
			username = "yudady"
			password = "這個密碼不能commit上去" 
		}
	}
}

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-web'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'

	implementation 'io.github.yudady:utils:0.0.2-SNAPSHOT'
	implementation 'io.github.yudady:bilibili-video:0.0.1-SNAPSHOT'
}
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

        mavenJava(MavenPublication) {
            //指定group/artifact/version信息
            group rootProject.ext.projectGroup
            artifactId = project.name
            version rootProject.ext.projectVersion

            // components.java jar包
            // components.web war包
            from components.java

            // 增加 sourcesJar、javadocJar 任务
            // artifact sourcesJar
            // artifact javadocJar
        }

        // bootJar is the default build task configured by Spring Boot
        //	mavenJava(MavenPublication) {
        //		group rootProject.ext.projectGroup
        //		artifactId = project.name
        //		version rootProject.ext.projectVersion
        //		// bootJar is the default build task configured by Spring Boot
        //		artifact bootJar
        //	}
    }

    repositories {
        maven {
            url = "file:///d:/tommy/github-repo/yudady/repo/maven2"
        }
    }
}
```

## helm-charts

```

```










