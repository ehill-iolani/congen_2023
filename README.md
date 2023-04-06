# congen_2023 codespace pilot

This is the pilot of using github codespace as an interactive cloud compute platform for dataprocessing.
There are 3 directories in the current repository:
1) arth
2) deca
3) fish

Each of these repositories contain a subset of the basecalled fastq data from their respective sequencing runs. 

You will use this as a template to generate a new codespace specifically for this project.
Once you are in the code space you will do the following:
```
docker pull ethill/decona_plus:mod
```

Choose one depending on your group:
```
docker run --name=arth_analysis --volume=/workspaces/congen_2023/arth:/home/data -it ethill/decona_plus:mod
docker run --name=deca_analysis --volume=/workspaces/congen_2023/deca:/home/data -it ethill/decona_plus:mod
docker run --name=fish_analysis --volume=/workspaces/congen_2023/fish:/home/data -it ethill/decona_plus:mod
```

Navigate to the data relevant to your group:
```
cd /home/data/
cd /home/data/
cd /home/data/
```

Begin the analysis:
```
# Arth
decona -f -l 170 -m 230 -q 10 -c 0.95 -n 5 -k 10 -T 4

# Fish
decona_pro -f -l 170 -m 230 -q 10 -c 0.95 -n 5 -k 10 -T 4 -B mifish_streamdb.fasta

# Shrimp
decona_pro -f -l 170 -m 230 -q 10 -c 0.95 -n 5 -k 10 -T 4 -B shrimp_db.fasta
```
