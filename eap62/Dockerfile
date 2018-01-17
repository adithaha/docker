FROM        openjdk:7-jdk-alpine

ENV         RESOURCES         /tmp/resources
ENV 	    EAP_PARENT        /usr/local
ENV 	    EAP_BINARY        /jboss-eap-6.2.0.zip
ENV	    EAP_DIR	      $EAP_PARENT/jboss-eap-6.2

ADD 	    resources $RESOURCES/

RUN         unzip $RESOURCES/binary/$EAP_BINARY -d $EAP_PARENT && \
	    cp -r $RESOURCES/modules $EAP_DIR && \
	    cp -r $RESOURCES/configuration $EAP_DIR/standalone && \
	    cp $RESOURCES/deployments/* $EAP_DIR/standalone/deployments

WORKDIR     $EAP_DIR/bin

CMD         ./standalone.sh -b 0.0.0.0
