FROM        glassfish:4.0

ENV         RESOURCES         /tmp/resources

ADD 	    resources/ $RESOURCES/

RUN         cp $RESOURCES/autodeploy/* /usr/local/glassfish4/glassfish/domains/domain1/autodeploy

WORKDIR     /usr/local/glassfish4

CMD         asadmin start-domain --verbose
