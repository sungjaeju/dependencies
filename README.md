plugins {
	id 'java'
	id 'org.springframework.boot' version '3.2.6'
	// id 'io.spring.dependency-management' version '1.1.5'
}

group = 'com.example'
version = '0.0.1-SNAPSHOT'

java {
	sourceCompatibility = '21'
	targetCompatibility = '21'
}

configurations {
	compileOnly {
		extendsFrom annotationProcessor
	}
}

repositories {
	// mavenCentral()
	flatDir {
      dirs 'dependencies'
  }
}

dependencies {
	// implementation 'org.springframework.boot:spring-boot-starter-web'
	// implementation 'org.projectlombok:lombok'
	// implementation 'org.springframework.boot:spring-boot-devtools'
	// implementation 'org.springframework.boot:spring-boot-configuration-processor'
	// implementation 'org.projectlombok:lombok'
	// implementation 'org.springframework.boot:spring-boot-starter-test'
	// implementation 'org.junit.platform:junit-platform-launcher'
 	implementation fileTree(dir: 'dependencies', include: ['*.jar'])
}

tasks.named('test') {
	useJUnitPlatform()
}

