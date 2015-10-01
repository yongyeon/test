########################################################################
# 
# ThunderMail6.0 Response 어플리케이션입니다.
#
# 반응정보 ( 오픈 , 클릭 등 )는 80포트로, 썬더메일 UI는 별도 포트로 서비스 할 경우
# 톰캣의 server.xml에 특정포트로 썬더메일UI를 셋팅 한 후
# 아래와 같이 80에 tm6-response를 추가 셋팅 한다. 
#
########################################################################
	<Service name="Catalina2">
	
	<Connector connectionTimeout="20000" port="80" protocol="HTTP/1.1" redirectPort="8443"/>
	
	<!-- Define an AJP 1.3 Connector on port 8009 -->
	<Connector port="8009" protocol="AJP/1.3" redirectPort="8443"/>
	
	<Engine defaultHost="localhost" name="Catalina2">
		<Realm className="org.apache.catalina.realm.UserDatabaseRealm" resourceName="UserDatabase"/>
		<!-- Define the default virtual host
		Note: XML Schema validation will not work with Xerces 2.2.
		-->
		<Host appBase="webapps" autoDeploy="true" name="localhost" unpackWARs="true" xmlNamespaceAware="false" xmlValidation="false">
		<Context docBase="tm6-response 소스 경로" path="" reloadable="true"/>
		</Host>
	</Engine>
	</Service>