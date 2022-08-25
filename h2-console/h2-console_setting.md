h2-console

h2콘솔에 접속되지 않을 때

application.properties 파일에 아래 항목을 적용 시킨다.

// 콘솔 접속 혀용
spring.h2.console.enabled=true
// sql문 보이기?
spring.jpa.show-sql=true
// url설정
spring.datasource.url=jdbc:h2:mem:testdb;MODE=MYSQL
// class이름 설정
spring.datasource.driver-class-name=org.h2.Driver
// user명 설정
spring.datasource.username=sa
// web에서 접근 허용 (spring security에서 h2콘솔에 접근하는 것을 막는데 이를 풀어준다.)
spring.h2.console.settings.web-allow-others=true

