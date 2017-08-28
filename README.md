# Armadillo_SNPs_WF_test
Files for a SNPs workflow with docker applications

Files came from https://bitbucket.org/snakemake/snakemake/
in directory Snakemake / docs / tutorial / workflow / data /

The Workflow is the equivalent of Snakemake Tutorial with few modification
All application exept Load Files are running with docker.

To test it you can use an ubuntu16.04 virtual machine
Open a terminal.
From your home directory, steps are :
    1  sudo apt-get update
    2  sudo apt-get install docker.io git unzip
    3  sudo usermod -aG docker $(whoami)
    4  sudo reboot # logout/login is enougth
    5  docker --version
You need an good answer

A way to install and compile source is with netbeans.
    6  sudo apt-get purge openjdk*
    7  sudo add-apt-repository ppa:webupd8team/java
    8  sudo apt-get update
    9  sudo apt-get install oracle-java8-installer
   10  wget http://download.netbeans.org/netbeans/8.2/final/bundles/netbeans-8.2-linux.sh
   11  chmod +x netbeans-8.2-linux.sh
   12  ./netbeans-8.2-linux.sh
Follow the steps dont forget to mention the path to jdk during the process
"/usr/lib/jvm/java-8-oracle"
or add it later in the netbeans config file in ~/netbeans-8.1/etc/netbeans.conf
with :
netbeans_jdkhome="/usr/lib/jvm/java-8-oracle"

   13  git clone https://github.com/JeGoi/armadillo2.git 
   14  git clone https://github.com/JeGoi/Armadillo_SNPs_WF_test.git
   15  cd Armadillo_SNPs_WF_test ; unzip inputs.zip

Run netbeans (icon on desktop), go to File/Open project Go to ~/ and select armadillo2
Then go to Run/Clean&BuildProject

Wait until it's done

Open a terminal
   14  cd ./armadillo2 ; cp dist/Armadillo.jar Armadillo.jar ; java -jar Armadillo.jar

Armadillo will start.

Go to File/Open project
Select your home directory (second icon on right of path)
Choose Armadillo_SNPs_WF_test/NGS_workflow_Sankemake_AB_Final_empty.txt
or Armadillo_SNPs_WF_test/NGS_workflow_Sankemake_ABC_Final_empty.txt

On the left side of the workflow, loading boxes are waiting. Double clic on them and choose the right file according the name box.
Genome file is in inputs/genome.fa
A fastq is in  inputs/samples/A.fastq
B fastq is in  inputs/samples/B.fastq
C fastq is in  inputs/samples/C.fastq

Enjoy.
