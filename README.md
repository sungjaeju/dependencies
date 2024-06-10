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
	// annotationProcessor 'org.springframework.boot:spring-boot-configuration-processor'
	// compileOnly 'org.projectlombok:lombok'
	// developmentOnly 'org.springframework.boot:spring-boot-devtools'
	// annotationProcessor 'org.projectlombok:lombok'
	// testImplementation 'org.springframework.boot:spring-boot-starter-test'
	// testRuntimeOnly 'org.junit.platform:junit-platform-launcher'

	// implementation 'org.springframework.boot:spring-boot-starter-webflux'
	// implementation 'org.springframework.boot:spring-boot-starter-validation'
	// implementation 'org.springframework.boot:spring-boot-starter-security'
	// implementation 'com.fasterxml.jackson.core:jackson-core:2.17.1'
	// implementation 'commons-codec:commons-codec:1.17.0'
	// implementation 'org.apache.commons:commons-lang3:3.14.0'
	// implementation 'org.apache.commons:commons-text:1.12.0'

	// implementation 'javax.xml.bind:jaxb-api:2.3.1'
	// implementation 'org.glassfish.jaxb:jaxb-runtime:4.0.5'
 
  	implementation fileTree(dir: 'dependencies', include: ['*.jar'])
	compileOnly files('libs/lombok-1.18.32.jar')
	annotationProcessor files('libs/lombok-1.18.32.jar')
	annotationProcessor files('libs/org.springframework.boot:spring-boot-configuration-processor')
  
}

tasks.named('test') {
	useJUnitPlatform()
}

task copyDependencies(type: Copy) {
   from configurations.compileClasspath
   into 'dependencies'
	 duplicatesStrategy = DuplicatesStrategy.EXCLUDE
}
