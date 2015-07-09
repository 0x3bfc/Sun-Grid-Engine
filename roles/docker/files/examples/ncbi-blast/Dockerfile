FROM ubuntu:12.04
MAINTAINER Ahmed Abullah <ahmedaabdulwahed@gmail.com>

# Install ncbi-blast
RUN apt-get update
RUN apt-get install -y ncbi-blast+
# Defualt BlastDB path
ADD . /blast_db
WORKDIR /blast_db
# Download Non-Redundant NCBI DB
RUN update_blastdb --passive --timeout 300 --force --verbose nr
RUN ls *.gz |xargs -n1 tar -xzvf
RUN rm *.gz.*
# Export BLASTDB Environment Variable
ENV BLASTDB /blast_db
