# Feature Extraction Approaches for Biological Sequences: A Comparative Study of Mathematical Models

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur eleifend tempor lacus et ultrices. Donec accumsan, augue semper elementum gravida, ante odio rhoncus magna, sit amet lacinia nisi tellus vitae ligula. Morbi congue sit amet dui quis aliquam. Vivamus vulputate id est id luctus. Quisque quis mi sit amet augue pellentesque auctor id ut arcu. Cras congue feugiat elementum. Integer et metus id leo iaculis pellentesque ut et nibh. Aliquam vitae justo dapibus velit tristique dapibus. Mauris lacinia faucibus feugiat. Proin sit amet ipsum odio. Curabitur ullamcorper ligula risus, nec fringilla augue laoreet vel. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur eleifend tempor lacus et ultrices. Donec accumsan, augue semper elementum gravida, ante odio rhoncus magna, sit amet lacinia nisi tellus vitae ligula. Morbi congue sit amet dui quis aliquam. Vivamus vulputate id est id luctus. Quisque quis mi sit amet augue pellentesque auctor id ut arcu. Cras congue feugiat elementum. Integer et metus id leo iaculis pellentesque ut et nibh. Aliquam vitae justo dapibus velit tristique dapibus. Mauris lacinia faucibus feugiat. Proin sit amet ipsum odio. Curabitur ullamcorper ligula risus, nec fringilla augue laoreet vel. 


## Authors

* Robson Parmezan Bonidia, Lucas Dias Hiera Sampaio, Douglas Silva Domingues, Alexandre Rossi Paschoal, Fabrı́cio Martins Lopes, André Carlos Ponce de Leon Ferreira de Carvalho, Danilo Sipoli Sanches

**Correspondence:** robservidor@gmail.com


## Publication

**Preprint:** BONIDIA, Robson Parmezan et al. Feature Extraction Approaches for Biological Sequences: A Comparative Study of Mathematical Models. bioRxiv, 2020.


## Table of contents
* [List of files](#list-of-files)
* [Dependencies](#dependencies)
* [Installing dependencies and package](#installing-dependencies-and-package)
* [Usage and Examples](#usage-and-uxamples)
    * [Preprocessing](#preprocessings)
    * [Mapping Numerical with Fourier Transform](#mapping-numerical-and-fourier-transform)
    * [Shannon and Tsallis Entropy](#shannon-and-tsallis-entropy)
    * [Complex Networks](#complex-networks)
* [Citation](#citation)


## List of files

 - **examples:** Files of Example;
 - **methods:** Main Files - Feature Extraction Models, e.g., Fourier, Numerical Mapping, Entropy, Complex Networks;
 - **preprocessing:** Preprocessing Files;
 - **README:** Documentation;
 - **requirements:** Dependencies.


## Dependencies

- Python (>=3.7.3)
- Biopython
- Igraph
- NumPy 
- Pandas
- SciPy


## Installing dependencies and package

It is important to note that we consider that the Python language is installed. Otherwise, access: https://www.python.org/downloads/release/python-375/.

```sh
$ git clone https://github.com/Bonidia/FeatureExtraction_BiologicalSequences FeatureExtraction

$ pip3 install -r requirements.txt

$ apt-get -y install python3-igraph
```


## Usage and Examples

In this section, 10 feature extraction methods are available: **7** numerical mapping techniques with Fourier transform, **2** techniques with Entropy, and **1** with Complex Networks.


### Preprocessing

Before executing any method in this package, it is necessary to run a pre-processing script, to eliminate any noise from the sequences (e.g., other letters as: N, K ...,). To use this script, follow the example below:

**Important:** This package only accepts sequence files in *Fasta* format as input to the methods.

```sh
Access folder: $ cd FeatureExtraction
 
To run the tool (Example): $ python3.7 -i input -o output


Where:

-i = Input - Fasta format file, e.g., test.fasta

-o = output - Fasta format file, e.g., test.csv
```

**Running:**

```sh
$ python3.7 -i dataset.fasta -o preprocessing.fasta 
```


### Mapping Numerical with Fourier Transform

To use this model, follow the example below:

```sh
To run the code (Example): $ python3.7 methods/FourierClass.py -i input -o output -l label -r representation


Where:

-i = Input - Fasta format file, e.g., test.fasta

-o = output - CSV format file, e.g., test.csv

-l = Label - Dataset Label, e.g., lncRNA, mRNA, sncRNA

-r = representation/mappings, e.g., 1 = Binary, 2 = Z-curve, 3 = Real, 4 = Integer, 5 = EIIP, 6 = Complex Number, 7 = Atomic Number.
```

**Running:**

```sh
$ python3.7 methods/FourierClass.py -i sequences.fasta -o sequences.csv -l mRNA -r 2
```


### Shannon and Tsallis Entropy

To use this model, follow the example below:

```sh
 
To run the tool (Example): $ python3.7 methods/EntropyClass.py -i input -o output -l mRNA -k k-mer -e Entropy


Where:

-i = Input - Fasta format file, e.g., test.fasta

-o = output - CSV format file, e.g., test.csv

-l = Label - Dataset Label, e.g., lncRNA, mRNA, sncRNA

-k = Range of k-mer, e.g., 1-mer (1) or 2-mer (1, 2)

-e = Type of Entropy, E.g., Shannon or Tsallis
```

**Running:**

```sh
$ python3.7 methods/EntropyClass.py -i sequences.fasta -o sequences.csv -l mRNA -k 10 -e Shannon
```


### Complex Networks

To use this model, follow the example below:

```sh
 
To run the tool (Example): $ python3.7 methods/ComplexNetworksClass.py -i input -o output -l mRNA -k kmer -t threshold


Where:

-i = Input - Fasta format file, e.g., test.fasta

-o = output - CSV format file, e.g., test.csv

-l = Label - Dataset Label, e.g., lncRNA, mRNA, sncRNA

-k = k size, e.g., 2, 3 (default = 3 (codon)), 4

-t = threshold size, e.g., 2, 3 (default = 10).
```

**Running:**

```sh
$ python3.7 methods/ComplexNetworksClass.py -i sequences.fasta -o sequences.csv -l mRNA -k 3 -t 10
```

## Citation

If you use this code in a scientific publication, we would appreciate citations to the following paper:

**Preprint:** BONIDIA, Robson Parmezan et al. Feature Extraction Approaches for Biological Sequences: A Comparative Study of Mathematical Models. bioRxiv, 2020.