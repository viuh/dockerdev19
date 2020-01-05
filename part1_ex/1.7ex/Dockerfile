FROM ubuntu:16.04 

WORKDIR /mydir 
RUN apt-get update && apt-get install -y curl 

COPY apu.sh ./
#RUN echo helsinki.fi | /mydir/apu.sh 
#RUN /mydir/apu.sh
#ENTRYPOINT ["/bin/bash"]

#RUN chmod u+x ./apu.sh
CMD ./apu.sh

