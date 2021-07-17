#Download base image centos latest 
#FROM ibmcom/powerai:1.6.1-base-ubuntu18.04-ppc64le as build
FROM ppc64le/ubuntu
ENV DEBIAN_FRONTEND=noninteractiv
#Dockerfile Mantainer
LABEL mantainer="clalogiudice@gmail.com"
USER root
#Update the centos software with yum package-manager
#RUN yum update -y && yum clean all
RUN apt update &&  apt upgrade -y

#Install git, wget and nano package
#RUN yum -y install git wget nano python2 && yum clean all
RUN apt install -y git wget nano samtools python2 build-essential zlib1g-dev libbz2-dev liblzma-dev python-dev
#gtf_splicesites

#RUN ln -s /usr/bin/python2 /usr/bin/python

RUN wget https://bootstrap.pypa.io/pip/2.7/get-pip.py \
    && python get-pip.py

RUN python -m pip install pysam

# Install IBM Advance Toolchain
#Run wget https://public.dhe.ibm.com/software/server/POWER/Linux/toolchain/at/ubuntu/dists/focal/6976a827.gpg.key \
#    && sudo apt-key add 6976a827.gpg.key
#Run sudo echo 'deb https://public.dhe.ibm.com/software/server/POWER/Linux/toolchain/at/ubuntu bionic at13.0' >> /etc/apt/sources.list \
#    && sudo apt update
#Run sudo apt-get -y install advance-toolchain-at13.0-runtime advance-toolchain-at13.0-devel advance-toolchain-at13.0-perf advance-toolchain-at13.0-mcore-libs
#ENV PATH=/opt/at12.0/bin:$PATH

# Install BWA
#RUN git clone https://github.com/yhcheng/bwa.git /code/bwa
#WORKDIR "/code/bwa"
#RUN make
ADD bwa /usr/bin/bwa

# Install STAR
#RUN git clone https://github.com/alexdobin/STAR.git /code/STAR
#WORKDIR "/code/STAR"
#RUN make

#RUN yum -y install bwa star bgzip tabix gtf_splicesites && yum clean all

#Clone Nature_protocol Git repository
RUN git clone https://github.com/BioinfoUNIBA/REDItools

WORKDIR "/REDItools/NPscripts/" 

#Install miniconda with conda packages required by the nature_protocol
#RUN chmod +x conda_pckg_installer_docker.py
#RUN ./conda_pckg_installer_docker.py
#ENV PATH /miniconda2/bin:$PATH
#RUN echo "source activate nature_protocol" >> ~/.bashrc

#PREPARE NATURE_PROTOCOL environment
#WORKDIR "/"
#RUN echo "python ./REDItools/NPscripts/download-prepare-data-NP_docker.py" >> /root/.bashrc
