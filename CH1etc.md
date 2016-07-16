#Ampliseq analysis

Sequenced as 10% input on Miseq PE250

Each ampliseq index has 5 unique PCR products -- 2 PCRs on 2 sgRNAs targeting the _CH1_ gene and 3 PCRs for for 3 sgRNAs targeting non-coding regions

--------

###Assemble overlapping paired-end reads 

Decided to use PEAR (link). Ran this analysis on a folder containing all 32 demultiplexed samples.

      
      for i in *.fq; do interleaveSwitcher.py u $i; done
      
      
