# Create Projects
oc new-project containerday-baseimg



#Create Build COnfig In OpenShift:
oc new-build --strategy docker --binary --name=siemens_jdk18



#Wrong Name!
#Try again:
oc new-build --strategy docker --binary --name=siemens-jdk18


#Create Dockerfile (DockerFile_1)
oc start-build siemens-jdk18 --from-file ./Dockerfile  --follow

# Root Required - User Dockerfile_2
cp Dockerfile_2 Dockerfile
oc start-build siemens-jdk18 --from-file ./Dockerfile  --follow


# Get Files (like Root CA) into it - User DOckerfile_3
cp Dockerfile_3 Dockerfile
oc start-build siemens-jdk18 --from-file ./Dockerfile  --follow

# Not all files are uploaded! Need to user --from-dir
oc start-build siemens-jdk18 --from-dir .  --follow


# Move the stuff to git!
oc delete buildconfig siemens-jdk18
oc new-build https://github.com/DanielFroehlich/containerday1-dockerbuild.git --name=siemens-jdk18
