![Pbrowser_logo.png](https://bitbucket.org/repo/oB7xMg/images/881255401-Pbrowser_logo.png)

# **Download the the last version of the Proteogenomics Browser:** #
https://bitbucket.org/jekroll/pb_base/get/master.zip

## **ABSTRACT** ##

**Motivation:** Visualization of mass spectrometry-based peptide identification is detrimental for proper publication standards of proteomics datasets. Genomic integration of such datasets are further desirable, specially for proteogenomic efforts where the characterization of MS data will lead to the identification of uncharacterized sequences such as those resulting from unpredicted exon joints, sequence polymorphisms or from non-coding regions.

**Results:** Hereby we describe the Proteogenomics Browser, a web-based tool that collects MS peptide identification, assigns exon usage, reports the identified protein isoforms with genomic alignments and, most importantly, also allows the inspection of MS2 information for proper peptide identification certainty. The Proteogenomics Browser was implemented and tested using three public MS datasets with excellent identification coverage for human culture cell lines and tissues.

**Availability and implementation:** The Proteogenomics Browser is written in Perl and is suitable to run only in UNIX (x86_64) systems. You can use the Proteogenomics Browser interface using our data through the following link: www.bioinformatics-brazil.org/protviewer/

**Sample files:** Maxquant output files, used for our online version of the Proteogenomics Browser, were made available at http://177.20.147.141/~jkroll/PBROWSER/maxdata


### Access our results by clicking here ###
[![protbrowser_view.png](https://bitbucket.org/repo/oB7xMg/images/1541595872-protbrowser_view.png)](http://www.bioinformatics-brazil.org/protviewer)


### To process your data to run with the Proteogenomics Browser: ###

```
> Download the last version of the Proteogenomics Browser:
  https://bitbucket.org/jekroll/pb_base/get/master.zip
> Decompress it in your folder
> Edit "config.cnf" (there are instructions inside the file)
> Run
  ./runall.pl config.cnf
> Enter into the results directory
  cd ./RESULTS_FOLDER_YOU_CHOSE
> Run the built-in http server (not needed, you can use Apache or any other software)
  ./runserver.sh
```


The Proteome Browser depends on some third-party softwares (compiled for x86_64 systems), which are already included in this bundle. If you use another kind of system, substitute the softwares from the folder "external" to match your system. Those softwares can be easily found elsewhere. Moreover, make sure your system has the softwares 'xz' and 'curl', which usually come together with almost GNU/Linux distributions.


ALERT: When running human samples, make sure your system has at least 32Gb of RAM.



## **config.cnf** ##
Example for a small analysis

```
#### SET THE SPECIE (all available species are listed elsewhere in this README)
pb_specie     homo_sapiens


#### SET THE OUTPUT FOLDER
pb_outfolder    ./RESULTS_MSMS


#### SET THE PROTEINS DATABASE (FASTA FILE)
db_proteins    uniprot.fasta


#### SET THE SAMPLES NAME AND DIRECTORY OF THE FILES "EVIDENCE" AND "MSMS", CREATED BY MAXQUANT
#### WHEN RUNNING MAXQUANT, REMEMBER THAT THE MSMS DATA MUST BE PROCESSED INDIVIDUALLY FOR EACH SAMPLE.

maxquant_evidence  GAMG  /data/GAMG/combined/txt/evidence.txt
maxquant_msms      GAMG  /data/GAMG/combined/txt/msms.txt

maxquant_evidence  HeLa  /data/Hela/combined/txt/evidence.txt
maxquant_msms      HeLa  /data/Hela/combined/txt/msms.txt

#### WHEN USING MzIdent FILES, SET THEM AS FOLLOWS:
#MzIdent    SAMPNAME     /dir/filename.mzIdent
```



All species available for the Proteome Browser:
```
ailuropoda_melanoleuca
anas_platyrhynchos
ancestral_alleles
anolis_carolinensis
astyanax_mexicanus
bos_taurus
caenorhabditis_elegans
callithrix_jacchus
canis_familiaris
cavia_porcellus
chlorocebus_sabaeus
choloepus_hoffmanni
ciona_intestinalis
ciona_savignyi
danio_rerio
dasypus_novemcinctus
dipodomys_ordii
drosophila_melanogaster
echinops_telfairi
equus_caballus
erinaceus_europaeus
felis_catus
ficedula_albicollis
gadus_morhua
gallus_gallus
gasterosteus_aculeatus
gorilla_gorilla
homo_sapiens
ictidomys_tridecemlineatus
latimeria_chalumnae
lepisosteus_oculatus
loxodonta_africana
macaca_mulatta
macropus_eugenii
meleagris_gallopavo
microcebus_murinus
monodelphis_domestica
mus_musculus
mustela_putorius_furo
myotis_lucifugus
nomascus_leucogenys
ochotona_princeps
oreochromis_niloticus
ornithorhynchus_anatinus
oryctolagus_cuniculus
oryzias_latipes
otolemur_garnettii
ovis_aries
pan_troglodytes
papio_anubis
pelodiscus_sinensis
petromyzon_marinus
poecilia_formosa
pongo_abelii
procavia_capensis
pteropus_vampyrus
rattus_norvegicus
saccharomyces_cerevisiae
sarcophilus_harrisii
sorex_araneus 
sus_scrofa
taeniopygia_guttata
takifugu_rubripes 
tarsius_syrichta
tetraodon_nigroviridis
tupaia_belangeri
tursiops_truncatus
vicugna_pacos
xenopus_tropicalis
xiphophorus_maculatus

