dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-web'
	compileOnly 'org.projectlombok:lombok'
	developmentOnly 'org.springframework.boot:spring-boot-devtools'
	annotationProcessor 'org.projectlombok:lombok'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
	testRuntimeOnly 'org.junit.platform:junit-platform-launcher'

	implementation 'org.springframework.boot:spring-boot-starter-webflux'
	implementation 'org.springframework.boot:spring-boot-starter-validation'
	implementation 'org.springframework.boot:spring-boot-starter-security'
	implementation 'com.fasterxml.jackson.core:jackson-core:2.17.1'
	implementation 'commons-codec:commons-codec:1.17.0'
	implementation 'org.apache.commons:commons-lang3:3.14.0'
	implementation 'org.apache.commons:commons-text:1.12.0'

	implementation 'javax.xml.bind:jaxb-api:2.3.1'
	implementation 'org.glassfish.jaxb:jaxb-runtime:4.0.5'
}
