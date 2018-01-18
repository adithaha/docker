FROM        rhel7-openjdk7

ENV         RESOURCES         /tmp/resources
ENV 	    EAP_PARENT        /home/jboss
ENV 	    EAP_BINARY        jboss-eap-6.2.0.zip
ENV	    EAP_DIR	      $EAP_PARENT/jboss-eap-6.2

ADD 	    resources $RESOURCES/

RUN 	    useradd -m jboss 

RUN	    chown -R jboss:jboss $EAP_PARENT

USER	    jboss

RUN	    unzip $RESOURCES/binary/$EAP_BINARY -d $EAP_PARENT && \
	    cp -r $RESOURCES/modules $EAP_DIR && \
	    cp -r $RESOURCES/configuration $EAP_DIR/standalone && \
	    cp $RESOURCES/deployments/* $EAP_DIR/standalone/deployments

RUN	    chmod 755 $EAP_PARENT && chmod -R 777 $EAP_DIR && chown -R jboss:jboss /home/jboss

USER	    1001

EXPOSE	    8080 9990

WORKDIR     $EAP_DIR/bin

CMD         ./standalone.sh -b 0.0.0.0
