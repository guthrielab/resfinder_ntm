# resfinder_ntm
Installation instructions for resfinder for the NTM project

## Installation
We recommend using pip to install Resfinder: https://pypi.org/project/resfinder/

`pip install resfinder` 

Ensure the following dependencies are also installed correctly in your PATH:

- KMA
- BLAST

Download the updated database that includes NTM by cloning the git repo:

`git clone https://github.com/guthrielab/resfinder_db.git`

`git clone https://github.com/guthrielab/pointfinder_db.git`

The disinfection database remains unchanged, so you can pull the original one from: https://bitbucket.org/genomicepidemiology/workspace/projects/DB

`git clone git clone https://bitbucket.org/genomicepidemiology/disinfinder_db/`

Index the databases 

## Running resfinder

To analyze FASTQ files:

`python -m resfinder -ifq sample01_R1.fastq.gz sample02_R2.fastq.gz -o output_directory -s "Mycobacterium abscessus" -db_res path/to/resfinder_db/ -db_point path/to/pointfinder_db/ -db_disinf path/to/disinfinder_db/ -acq -c`

To analyse genome assemblies:

`python -m resfinder -ifa sample01.fasta -o output_directory -s "Mycobacterium abscessus" -db_res path/to/resfinder_db/ -db_point path/to/pointfinder_db/ -db_disinf path/to/disinfinder_db/ -acq -c`
