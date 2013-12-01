SME
===
The architecture of this package has been designed by **Xavier Glorot** (https://github.com/glorotxa), with some contributions from **Antoine Bordes** (https://www.hds.utc.fr/~bordesan).

**Update (Nov 13):** the code for Translating Embeddings (see https://www.hds.utc.fr/everest/doku.php?id=en:transe) has been included along with a new version for Freebase (FB15k).

1. Overview
-----------------------------------------------------------------

This package proposes scripts using Theano to perform training and evaluation on several datasets of the models: 
- **Structured Embeddings** (SE) defined in (Bordes et al., AAAI 2011);
- **Semantic Matching Energy** (SME_lin & SME_bil) defined in (Bordes et al., MLJ 2013);
- *NEW* **Translating Embeddings** (TransE) defined in (Bordes et al., NIPS 2013).

Please refer to the following pages for more details and references:  
- https://www.hds.utc.fr/everest/doku.php?id=en:smemlj12
- *NEW* https://www.hds.utc.fr/everest/doku.php?id=en:transe

Content of the package:
- model.py : contains the classes and functions to create the different models and Theano functions (training, evaluation...).
- {dataset}_exp.py : contains an experiment function to train all the different models on a given dataset.
- The data/ folder contains the data files for the learning scripts.
- in the {dataset}/ folders:
	* {dataset}_parse.py : parses and creates data files for the training script of a given dataset.
	* {dataset}_evaluation.py : contains evaluation functions for a given dataset.
	* {dataset}\_{model_name}.py : runs the best hyperparameters experiment for a given dataset and a given model.
	* {dataset}\_{model_name}.out : output we obtained on our machines for a given dataset and a given model using the script above.
	* {dataset}_test.py : perform quick runs for small models of all types to test the scripts.

The datasets currently available are:
 * **Multi-relational benchmarks** (Kinhsips, UMLS & Nations -- Tensor folder) to be downloaded from https://www.hds.utc.fr/everest/doku.php?id=en:smemlj12
 * **WordNet** (WN folder) to be downloaded from https://www.hds.utc.fr/everest/doku.php?id=en:smemlj12
 * **Freebase** (FB folder) used in (Bordes et al., AAAI 2011) to be downloaded from https://www.hds.utc.fr/everest/doku.php?id=en:smemlj12
 * *NEW* **Freebase15k** (FB15k folder)  used in (Bordes et al., NIPS 2013) to be downloaded from https://www.hds.utc.fr/everest/doku.php?id=en:transe



2. 3rd Party Libraries
-----------------------------------------------------------------

You need to install Theano to use those scripts. It also requires: Python >= 2.4, Numpy >=1.5.0, Scipy>=0.8.
The experiment scripts are compatible with Jobman but this library is not mandatory.


3. Installation
-----------------------------------------------------------------

Put the script folder in your PYTHONPATH.


4. Data Files Creation
-----------------------------------------------------------------

Put the absolute path of the downloaded dataset (from: https://www.hds.utc.fr/everest/doku.php?id=en:smemlj12 or  https://www.hds.utc.fr/everest/doku.php?id=en:transe) at the beginning of the {dataset}_parse.py script and run it (the SME folder has to be your current directory). Note: Running Tensor_parse.py generates data for both Kinhsips, UMLS & Nations.

5. Training and Evaluating a Model
-----------------------------------------------------------------

Simply run the corresponding {dataset}_{model_name}.py file (the SME/{dataset}/ folder has to be your current directory) to launch a training. When it's over, running {dataset}_evaluation.py with the path to the best_valid_model.pkl of the learned model runs the evaluation on the test set

6. Citing
-----------------------------------------------------------------

If you use this code, you could provide the link to the github page: https://github.com/glorotxa/SME . Also, depending on the model used, you should cite the *Structured Embeddings** paper (Bordes et al., AAAI 2011), the **Semantic Matching Energy** one (Bordes et al., MLJ 2013) or the  **Translating Embeddings** one (Bordes et al., NIPS 2013).

