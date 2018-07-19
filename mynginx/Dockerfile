FROM centos:7

# Nginx is in the EPEL, so we need to install epel-release first
#
# It is good practice to clean the Yum cache after every "yum install"
# to avoid cache files bloating the layer
#   (Same applies for apt-get on Debian-based OS)
RUN yum install -y epel-release && \
    yum install -y nginx && \
    yum clean all

# Install index.html from the build context at the Nginx content root
COPY index.html /usr/share/nginx/html

EXPOSE 80

# Run Nginx in foreground mode as the container command
CMD ["nginx", "-g", "daemon off;"]
