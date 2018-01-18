#########################################################################
# HOW									#
# 1. Put jboss-eap-6.2.0.zip in resources/binary folder			#
# 2. Put your war or ear file into resources/deployments 		#
# 3. Put your customized configuration files in resources/configuration	#
# 4. Put your customized module files in resources/modules		#
# 5. Build image							#
# 6. Run your container							#
#########################################################################

# build image
docker build -t rhel7-openjdk7 .

# run container
docker run -d --name=eap62-sample -p 8080:8080 eap62-sample

# debug container
docker run -it --rm --name=eap62-sample -p 8080:8080 eap62-sample /bin/sh


docker rm eap62-sample
