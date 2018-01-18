FROM        rhel7-openjdk7

ENV         RESOURCES         /tmp/resources
ENV 	    GF4_PARENT        /home/jboss
ENV 	    GF4_BINARY        glassfish-4.0.zip
ENV	    GF4_DIR	      $GF4_PARENT/glassfish4

ADD 	    resources $RESOURCES/

RUN 	    useradd -m jboss 

RUN	    chown -R jboss:jboss $GF4_PARENT

USER	    jboss

RUN	    unzip $RESOURCES/binary/$GF4_BINARY -d $GF4_PARENT && \
	    cp $RESOURCES/autodeploy/* $GF4_DIR/glassfish/domains/domain1/autodeploy 

RUN	    chmod 755 $GF4_PARENT && chmod -R 777 $GF4_DIR && chown -R jboss:jboss /home/jboss

USER	    1001

EXPOSE	    8080

WORKDIR     $GF4_DIR/bin

CMD         ./asadmin start-domain --verbose
