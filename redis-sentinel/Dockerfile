ARG THUMBOR_TAG=latest
FROM thumbor_thumbor:$THUMBOR_TAG

LABEL maintainer="Brian Myers"

#
#
#
#
#VOLUME /data

#ADD /prometheus /prometheus
#ENV HOME /app
#ENV SHELL bash
#ENV WORKON_HOME /app
#WORKDIR /app
#
#RUN pip install -e ../prometheus/

#RUN  \
#    apt-get update && \
#    apt-get -y upgrade && \
#    apt-get -y autoremove && \
#    apt-get install -y -q redis-server && \
#    apt-get clean



ADD /prometheus /prometheus
ADD /redis /redis
ENV HOME /app
ENV SHELL bash
ENV WORKON_HOME /app
WORKDIR /app

COPY requirements.txt /app/requirements.txt
RUN pip install --trusted-host None --no-cache-dir \
   -r /app/requirements.txt
RUN pip install -e ../prometheus/
RUN pip install -e ../redis/



#ADD requirements.txt /app
#WORKDIR /app
#RUN pip install -r requirements.txt


#ENV HOME /app
#ENV SHELL bash
#ENV WORKON_HOME /app
#WORKDIR /app
#
#COPY requirements.txt /app/requirements.txt
#RUN pip install --trusted-host None --no-cache-dir \
#   -r /app/requirements.txt

#COPY docker-entrypoint.sh /
#ENTRYPOINT ["/docker-entrypoint.sh"]
#CMD ["remotecv"]
