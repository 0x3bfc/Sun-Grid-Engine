#NCBI-Blast

Build NCBI-Blast Image
-------------------------

NCBI-Blast Docker file downloads nr database which included in your blast docker image, so to avoid downloading, simply comment the lines 11,12,13
then run the following command line, and instead of that download your databased in a different directory then attach this directory to your container as 
a data volume

	$ sudo docker build -t blast .


Run NCBI-Blast Container
------------------------

Run the following command line to test blast with built-in nr database.


	$ sudo docker run --rm blast bash -c 'blastp -db nr -query somesequence.fasta'

or by attaching database data volume to a running container

	$ sudo docker run --rm -v /src/blast_db/nr:/blast_db blast bash -c 'blastp -db nr -query somesequence.fasta'


