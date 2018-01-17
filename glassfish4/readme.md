#################################################################
# HOW								#
# 1. Put your war or ear file in resources/autodeploy 		#
# 2. Build image						#
# 3. Run your container						#
#################################################################

# build image
docker build -t glassfish4-sample .

# run container
docker run -d --name=glassfish4-sample -p 8180:8080 glassfish4-sample

# debug container
docker run -it --rm --name=glassfish4-sample -p 8180:8080 glassfish4-sample /bin/sh
