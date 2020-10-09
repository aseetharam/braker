
Bootstrap: docker
From: arnstrm2/augustus


%labels
   MAINTAINER Arun Seetharam
   EMAIL arnstrm@iastate.edu

%post
   apt-get -y update
   apt-get -y install exonerate
   apt-get -y install ncbi-blast+
   apt-get -y install cdbfasta
   apt-get -y install diamond-aligner
   apt-get -y install python3-pip
   apt-get -y install openjdk-8-jdk
   apt-get -y install cmake
   cpan CPAN
   cpan File::Spec::Functions \
        YAML \
        Hash::Merge \
        List::Util \
        Thread::Queue \
        Logger::Simple \
        Module::Load::Conditional \
        Parallel::ForkManager \
        POSIX Scalar::Util::Numeric \
        YAML Math::Utils \
        MCE::Mutex \
        threads \
        File::HomeDir \
        List::MoreUtils
   pip3 install biopython
   # install GeneMark-ES
   cd /root
   wget http://topaz.gatech.edu/GeneMark/tmp/GMtool_fS3HC/gmes_linux_64.tar.gz
   wget http://topaz.gatech.edu/GeneMark/tmp/GMtool_fS3HC/gm_key_64.gz
   gunzip gm_key_64.gz
   mv gm_key_64 ~/.gm_key
   tar xf gmes_linux_64.tar.gz
   rm -rf gmes_linux_64.tar.gz
   cd /root/gmes_linux_64
   ./change_path_in_perl_scripts.pl "/usr/bin/env perl"
   # install bamtools
   cd /root
   wget https://github.com/pezmaster31/bamtools/archive/v2.5.1.tar.gz
   tar xf v2.5.1.tar.gz
   rm -rf v2.5.1.tar.gz
   cd bamtools-2.5.1 && \
      mkdir build && \
      cd build && \
      cmake .. && \
      make && \
      make install 
   cd /root
   git clone https://github.com/Gaius-Augustus/GUSHR.git
   git clone https://github.com/Gaius-Augustus/BRAKER.git


%environment
  export PATH=$PATH:/root/gmes_linux_64:/root/augustus/bin:/root/augustus/scripts:/root/GUSHR:/root/BRAKER/scripts
  export PERL5LIB=$PERL5LIB:/root/gmes_linux_64/lib


