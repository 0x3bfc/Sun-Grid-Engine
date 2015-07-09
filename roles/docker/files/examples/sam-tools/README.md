#SAM-Tools

Build SAM-Tools Image

	$ sudo docker build -t samtools .

or simply pull samtools docker image:

        $ sudo docker pull ahmedabd/biodocker:samtools

Run the following command line to test samtools

	$ sudo docker run --rm samtools bash -c 'samtools'

