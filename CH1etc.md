#Ampliseq analysis

Sequenced as 10% input on Miseq PE250

Each ampliseq index has 5 unique PCR products -- 2 PCRs on 2 sgRNAs targeting the _CH1_ gene and 3 PCRs for for 3 sgRNAs targeting non-coding regions

--------

###Assemble overlapping paired-end reads 

Decided to use Pear (link) to assemble the overlapping paired-end reads. Ran this analysis on a folder containing all 32 demultiplexed samples.

First, have to uninterleave the files for Pear:

      
      for i in *.fq 
      do 
        interleaveSwitcher.py u $i 
      done
      

Next up run Pear on all the uninterleaved files:

      
      for i in *-1.fq
      do
        BASE=$(basename $i -1.fq)
        echo 'processing' $BASE
        pear-0.9.6-bin-64 -f $BASE-1.fq -r $BASE-2.fq -o $BASE-pear
        echo 'done'
      done
      


