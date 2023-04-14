# Blast-comparaison-sequence
#comparaison de sequence de nucleotide et de protéine avec blast en bash puis étude statistique et graphiques avec rstudio

#Possibilité d'utiliser un SCRIPT BASH pour réaliser le BLAST des séquences : 


#!/bin/bash


#SBATCH --job-name=18S_blast
#SBATCH --output=/shared/projects/carefree/Archives/test_jobcluster_%j.out


#SBATCH --mail-user lokianlga@gmail.com
#SBATCH --mail-type ALL


#SBATCH --time=24:00:00


#SBATCH --partition=fast


#SBATCH --nodes=1
#SBATCH --cpus-per-task=10
#SBATCH --mem=32GB


cd /shared/projects/carefree/Archives/test_jobcluster


#installation de blast
module load blast/2.13.0


# permet d'afficher la date de début


echo -e "\n##########################################"
echo -e "Blast des séquences de 18S"
echo -e "##########################################\n"


date


echo -e "\n"
#création de la database avec les sequences
makeblastdb -in /shared/projects/carefree/Archives/test_jobcluster/allseq -out /shared/projects/carefree/Archives/test_>


#blast de nos sequences
blastn -query /shared/projects/carefree/Archives/test_jobcluster/allseq -db /shared/projects/carefree/Archives/test_job>


# permet d'afficher la date de fin
date


echo -e "\n##########################################"
echo -e "Blast des séquences de 18S"
echo -e "##########################################\n"
