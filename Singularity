Bootstrap: docker
From: ubuntu:18.04

%environment
export AUGUSTUS_CONFIG_PATH=/usr/share/augustus/config
export PERL5LIB=$PERL5LIB:/opt/gmes_linux_64/lib
export PATH=$PATH:/opt/gmes_linux_64
export PATH=$PATH:/opt/gth/bin
export PATH=$PATH:/opt/BRAKER/scripts


%post
apt-get update
apt-get install -y build-essential wget curl git autoconf
apt-get install -y libgsl-dev libboost-all-dev libsuitesparse-dev liblpsolve55-dev
apt-get install -y libsqlite3-dev libmysql++-dev
apt-get install -y libboost-iostreams-dev zlib1g-dev
apt-get install -y libbamtools-dev
apt-get install -y libbz2-dev liblzma-dev
apt-get install -y libncurses5-dev
apt-get install -y libssl-dev libcurl3-dev
apt-get install -y libboost-all-dev 
apt-get install -y samtools bamtools bcftools
apt-get install -y cdbfasta
apt-get install -y ncbi-blast+ diamond-aligner exonerate
apt-get install -y libhdf5-dev
apt-get install -y augustus augustus-data augustus-doc
apt-get install -y python3-pip
pip3 install biopython
apt-get install -y cpanminus
cpanm install File::Spec::Functions
cpanm install Hash::Merge
cpanm install File::HomeDir
cpanm install List::Util
cpanm install Logger::Simple 
cpanm install Module::Load::Conditional
cpanm install Parallel::ForkManager
cpanm install POSIX Scalar::Util::Numeric
cpanm install YAML 
cpanm install Math::Utils
cpanm install MCE::Mutex
cpanm install threads
cd /opt
wget https://genomethreader.org/distributions/gth-1.7.1-Linux_x86_64-64bit.tar.gz
tar xf gth-1.7.1-Linux_x86_64-64bit.tar.gz
rm gth-1.7.1-Linux_x86_64-64bit.tar.gz
mv gth-1.7.1-Linux_x86_64-64bit gth
export PATH=$PATH:/opt/gth/bin
cd /opt
wget http://topaz.gatech.edu/GeneMark/tmp/GMtool_keR4u/gmes_linux_64.tar.gz
tar xf gmes_linux_64.tar.gz
rm gmes_linux_64.tar.gz
wget http://topaz.gatech.edu/GeneMark/tmp/GMtool_keR4u/gm_key_64.gz
gunzip gm_key_64.gz
mv gm_key_64 ~/.gm_key
cd /opt
git clone https://github.com/Gaius-Augustus/BRAKER.git

