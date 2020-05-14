FROM centos
MAINTEAINER denven<myemail@foxmail.com>

COPY c.txt /usr/local/cincontainer.txt
ADD jdk-8u171-linux-x64.tar.gz /usr/local/
ADD apache-tomcat-9.0.8.tar.gz /usr/local/

RUN yum -y install vim

ENV MY_PATH /usr/local
WORKDIR $MY_PATH

ENV JAVA_HOME /usr/local/jdk1.8.0_171
ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV CATALINA_HOME /usr/local/apache-tomcat-9.0.8
ENV CATALINA_BASE /usr/local/apache-tomcat-9.0.8
ENV PATH $PATH:$JAVA_HOME/bin:$CATALINA_HOME/lib:$CATALINA_HOME/bin

EXPOSE 8080

# ENTRYPOINT ["/usr/local/apache-tomcat-9.0.8/bin/startup.sh"]
# CMD ["/usr/local/apache-tomact-9.0.8/bin/catalina.sh", "run"]
CMD /usr/local/apache-tomact-9.0.8/bin/catalina.sh && tail -F /usr/local/apache-tomcat-9.0.8/bin/logs/catalina.out
