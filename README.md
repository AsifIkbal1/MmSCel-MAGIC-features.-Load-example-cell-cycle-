# MmSCel-MAGIC-features.-Load-example-cell-cycle-
MmSCel🧬MAGIC features. Load example, cell cycle 
# What is about ? 

**Briefly:** Example how to work with huge .h5 files without loading them in RAM. 
See also example in https://www.kaggle.com/code/alexandervc/use-h5py-for-huge-h5-file-backing-it-on-disk 

**Data** from the competition , but denoising preprocessing by MAGIC package (https://github.com/KrishnaswamyLab/MAGIC) has been done by Liza Geraseva. See discussion: https://www.kaggle.com/competitions/open-problems-multimodal/discussion/350856

**Work principle:** The main data can be accessed as f['0']['block0_values'] - without loading to RAM, but  when one takes a slice: f['0']['block0_values'][:,IX] - it is converted to numpy array (and loaded into memory?). 
There are some details: one can do constant slices like  f['0']['block0_values'][:10,:10], but to make a  variable slice one need to process in two steps: f['0']['block0_values'][:,IX1][IX0]. 

**Details:** We load the data. And as an exercise and sanity check we produce plots for cell proliferation cycle visualization - so-called G1/S-G2/M plots. The results are as expected - the "cyclic" structes is better seen comparing as to original files (see version 3 of the present notebook). Remark: one can compare with another (more simple denoising ("pooling")) here: https://www.kaggle.com/code/alexandervc/mmscel-cell-cycle-03-daybydaychange-megakaryocyte#G1/S-G2/M-plots-to-analyse-the-cell-cycle

**Context:** See paper: https://arxiv.org/abs/2208.05229 for cell cycle analysis. "Computational challenges of cell cycle analysis using single cell transcriptomics" Alexander Chervov, Andrei Zinovyev. All the work for that paper has been done on Kaggle - see datasets and code therein: https://www.kaggle.com/alexandervc/datasets?scroll=true https://www.kaggle.com/andreizinovyev Hundreds of single cell RNA seq datasets were analyzed.



### Remarks: 
    
    ( in Vesrstion 1- 6 we look mainly on Megakaryocyte Progenitors - just almost smallest and representative (from previous analysis ) 

### Versions:

#### 11 with MAGIC again 

#### 10 - for comparaison - same data as 9, but NO MAGIC 


#### 9 - added plots all cell types
    
    Same MAGIC CITEseq TEST

#### 7,8 cosmetic changes


#### 6 - return to MAGIC - same as version 4 - "test" part of CITE-seq (features)
        

#### 5 - for comparaison  NO(!) MAGIC - difference is STRIKING

    For days 2,4 - we cannot see clear "cyclic" structures without denoising.
    Compare with denoised versions - where "cyclic" structure can be clearly seen ! (E.g. version 4) 
    "test" part of CITE-seq (features)


#### 4 - MAGIC on "test" part of CITE-seq (features)

    "Cyclic" structure is seen VERY well for many days - may be because only one donor, but for "train" part we have 3 donors and they mix and create less clear picture

#### 3 - for comparaison look on original input file

    The "cyclic" structure is less clearly seen for original files, comparing to denoised - as expected. 

#### 1,2 - work with MAGIC denoised data. 

