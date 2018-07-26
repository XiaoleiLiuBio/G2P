# G2P [![](https://img.shields.io/badge/Issues-0%2B-brightgreen.svg)](https://github.com/XiaoleiLiuBio/G2P/issues) [![](https://img.shields.io/badge/Release-v1.0.1-blue.svg)](https://github.com/XiaoleiLiuBio/G2P/commits/master)

## A Pre-Genome-Wide-Association-Study Tool for [G](https://github.com/XiaoleiLiuBio/G2P)enotype Simulation, [P](https://github.com/XiaoleiLiuBio/G2P)henotype Simulation, and [P](https://github.com/XiaoleiLiuBio/G2P)ower Evaluation

<p align="center">
<a href="https://raw.githubusercontent.com/XiaoleiLiuBio/G2P/master/results/G2P_logo.png">
<img src="results/G2P_logo.png" height="250px" width="450px">
</a>
</p>

### Authors:

> You Tang and ***Xiaolei Liu***

### Contact:
> [xiaoleiliu@mail.hzau.edu.cn](Xiaolei Liu)

### Contents
<!-- TOC updateOnSave:false -->

- [Installation](#installation)
    - [Environment Setup](#environment-setup)
    - [Windows](#windows)
    - [MAC](#mac)
    - [Linux](#linux)
- [Data Preparation](#data-preparation)
    - [.ped](#.ped)
    - [.map](#.map)
    - [.pop](#.pop)
- [Genotype Simulation](#genotype-simulation)
    - [Random Simulation - GUI](#random-simulation-gui)
    - [Single Population - GUI](#single-population-gui)
    - [Multiple Population - GUI](#multiple-population-gui)
    - [Random Simulation - Pipeline](#random-simulation-pipeline)
    - [Single Population - Pipeline](#single-population-pipeline)
    - [Multiple Population - Pipeline](#multiple-population-pipeline)
- [Phenotype Simulation](#phenotype-simulation)
    - [Phenotype - GUI](#phenotype-gui)
    - [Phenotype - Pipeline](#phenotype-pipeline)
- [Population Structure](#population-structure)
    - [PC - GUI](#pc-gui)
    - [PC - Pipeline](#pc-pipeline)
- [GWAS](#gwas)
    - [GWAS - GUI](#gwas-gui)
    - [GWAS - Pipeline](#gwas-pipeline)
- [Method Evaluation](#method-evaluation)
    - [Method Evaluation - GUI](#method-evaluation-gui)
    - [Method Evaluation - Pipeline](#method-evaluation-pipeline)
- [FAQ and Hints](#faq-and-hints)

<!-- /TOC -->

---
# Installation
**[back to top](#contents)**  

## Environment Setup
**[back to top](#contents)**  
**JDK1.8 should be installed and environment variables must be configured before using G2P (http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**  
## Windows  
**[back to top](#contents)**  
**GUI**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/gG2P_win_64 and double click the .jar file  
**Pipeline**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/kG2P_win_64 and  
## Mac  
**[back to top](#contents)**  
**GUI**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/gG2P_mac and double click the .jar file  
**Pipeline**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/kG2P_mac  
*permission setting*  
```bash
$ chmod 777 gemma oldplink plink  
```
## Linux  
**[back to top](#contents)**  
**GUI**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/gG2P_linux_x86_64 
and run 
```bash
$ Java -jar gG2P.jar  
```
**Pipeline**  
Download all files from https://github.com/XiaoleiLiuBio/G2P/tree/master/kG2P_linux_x86_64  
*permission setting*  
```bash
$ chmod 777 gemma oldplink plink  
```

# Data Preparation
*All files should be prepared with the same prefix*
## .ped  
*details see http://zzz.bwh.harvard.edu/plink/data.shtml#ped*
**[back to top](#contents)** 

|Family ID|Individual ID|Father ID|Mother ID|Sex|Trait|marker 1|marker 2|marker 3|marker 4|marker 5|marker 6|
| :---: | :---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
|1|33-16|	0|	0|	0|	2|	0 0|	A A|	A A|	A G|	A G|	A G|
|1|38-11|	0|	0|	0|	2|	0 0|	A G|	A G|	A A|	A G|	A G|
|1|4226	|	0|	0|	0|	2|	0 0|	A G|	A A|	A A|	A G|	A G|
|1|4722|	0|	0|	0|	2|	0 0|	A G|	A G|	A A|	A G|	A G|
|1|A188	|	0|	0|	0|	2|	0 0|	A A|	A A|	A A|	A G|	A G|
|1|A214N|	0|	0|	0|	2|	0 0|	A G|	A A|	A G|	A A|	A G|
|1|A239	|	0|	0|	0|	2|	0 0|	A A|	A A|	A G|	A G|	A A|

|Family ID|Individual ID|Father ID|Mother ID|Sex|Trait|marker 1|marker 2|marker 3|marker 4|marker 5|marker 6|
| :---: | :---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
|1|33-16|	0|	0|	0|	2|	0 0|	1 1|	1 1|	1 3|	1 3|	1 3|
|1|38-11|	0|	0|	0|	2|	0 0|	1 3|	1 3|	1 1|	1 3|	1 3|
|1|4226	|	0|	0|	0|	2|	0 0|	1 3|	1 1|	1 1|	1 3|	1 3|
|1|4722|	0|	0|	0|	2|	0 0|	1 3|	1 3|	1 1|	1 3|	1 3|
|1|A188	|	0|	0|	0|	2|	0 0|	1 1|	1 1|	1 1|	1 3|	1 3|
|1|A214N|	0|	0|	0|	2|	0 0|	1 3|	1 1|	1 3|	1 1|	1 3|
|1|A239	|	0|	0|	0|	2|	0 0|	1 1|	1 1|	1 3|	1 3|	1 1|

## .map  
*details see http://zzz.bwh.harvard.edu/plink/data.shtml#map*
**[back to top](#contents)** 

|Chromosome ID|Marker ID|Genetic Distance|Physical Distance|
| :---: | :---: |:---: |:---: |
|1|	PZB00859.1|	0|	157104|
|1|	PZA01271.1|	0|	1947984|
|1|	PZA03613.2|	0|	2914066|
|1|	PZA03613.1|	0|	2914171|
|1|	PZA03614.2|	0|	2915078|
|1|	PZA03614.1|	0|	2915242|
|1|	PZA00258.3|	0|	2973508|

## .pop  
**[back to top](#contents)**  

|Sample ID|sub-Population ID|
| :---: | :---: |
|33-16|	1|	
|38_11|	1|	
|4226|	1|	
|4722|	2|	
|A188|	2|	
|A214N|	2|	
|A239|	2|	
|A272|	2|	
|A441-5|	2|	
|A554|	3|	
|A556|	3|	
|A6|	3|		
|A619|	3|

# Genotype Simulation  
## Random Simulation  
**[back to top](#contents)** 

<p align="center">
<a href="https://raw.githubusercontent.com/XiaoleiLiuBio/G2P/master/results/Random Simulation 2.png">
<img src="results/Random Simulation 2.png" height="460px" width="460px">
</a>
</p>


