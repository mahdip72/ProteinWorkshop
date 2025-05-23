### 0.2.6 (UNRELEASED)

### Datasets
* Correct stage-based conditions mentioned in notebook tutorials [#92](https://github.com/a-r-j/ProteinWorkshop/pull/92)
* Add stage-based conditions to `setup` in `ProteinDataModule` [#72](https://github.com/a-r-j/ProteinWorkshop/pull/72)
* Improves support for datamodules with multiple test sets. Generalises this to support GO and FOLD. Also adds multiple seq ID.-based splits for GO. [#72](https://github.com/a-r-j/ProteinWorkshop/pull/72)
* Add redownload checks for already downloaded datasets and harmonise pdb download interface [#86](https://github.com/a-r-j/ProteinWorkshop/pull/86)
* Remove remaining errors from PDB dataset change
* Add option to create pdb datasets with sequence-based splits [#88](https://github.com/a-r-j/ProteinWorkshop/pull/88) as well as time-based splits [#89](https://github.com/a-r-j/ProteinWorkshop/pull/89)

### Models

* Adds missing `pos` attribute to GearNet `required_batch_attributes` (fixes [#73](https://github.com/a-r-j/ProteinWorkshop/issues/73)) [#74](https://github.com/a-r-j/ProteinWorkshop/pull/74)
* Fixes PDB download failure due to missing protein data [#77](https://github.com/a-r-j/ProteinWorkshop/pull/77)
* Add support for handling training/validation OOMs gracefully [#81](https://github.com/a-r-j/ProteinWorkshop/pull/81)
* Add support for handling backward OOMs gracefully [#83](https://github.com/a-r-j/ProteinWorkshop/pull/83)
* Update GCPNet paper link [#85](https://github.com/a-r-j/ProteinWorkshop/pull/85)
* Add ability for `BenchmarkModel` to have its decoder disabled [#101](https://github.com/a-r-j/ProteinWorkshop/pull/101)
* Fix dtype mismatch in `gcp.py` that broke Automatic Mixed Precision (AMP) training [#102](https://github.com/a-r-j/ProteinWorkshop/pull/102)

### Framework

* Adds `InverseSquareRoot` LR scheduler [#71](https://github.com/a-r-j/ProteinWorkshop/pull/71)

### Command
* Adds `--force-cuda-version` to `workshop install` [#78](https://github.com/a-r-j/ProteinWorkshop/pull/78)

### Features
* Fix `sequence_edges` behaviour when argument `b` is a `Data` object [#80](https://github.com/a-r-j/ProteinWorkshop/pull/80)

### Misc
* Update ICLR paper link and citation [#82](https://github.com/a-r-j/ProteinWorkshop/pull/82)
* Add an optional group for installing plotting and analysis specific libraries to lighten the install of the core framework [#90](https://github.com/a-r-j/ProteinWorkshop/pull/90)

### 0.2.5 (28/12/2023)

#### Datasets

* Adds to antibody-specific datasets using the IGFold corpuses for paired OAS and Jaffe 2022 [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Set `in_memory=True` as default for most (small) datasets for improved performance [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Fix `num_classes` for GO datamodules * Set `in_memory=True` as default for most (downstream) datasets for improved performance [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Fixes GO labelling [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)

### Features

* Improves positional encoding performance by adding a `seq_pos` attribute on `Data/Protein` objects in the base dataset getter. [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Ensure correct batched computation of orientation features. [#58](https://github.com/a-r-j/ProteinWorkshop/pull/58/)

### Models

* Implement ESM embedding encoder ([#33](https://github.com/a-r-j/ProteinWorkshop/pull/33), [#41](https://github.com/a-r-j/ProteinWorkshop/pull/33))
* Adds CDConv implementation [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Adds tuned hparams for models [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)

### Framework

* Refactors beartype/jaxtyping to use latest recommended syntax [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Adds explainability module for performing attribution on a trained model [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Change default finetuning features in config: `ca_base` -> `ca_seq` [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Add optional hparam entry point to finetuning config [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Fixes GPU memory accumulation for some metrics [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Updates zenodo URL for processed datasets to reflect upstream API change [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Adds multi-hot label encoding transform [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Fixes auto PyG install for `torch>2.1.0` [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Adds `proteinworkshop.model_io` containing utils for loading trained models [#53](https://github.com/a-r-j/ProteinWorkshop/pull/53/)
* Add script for plotting UMAP embeddings of any dataset given a pre-trained encoder model

### 0.2.4 (10/09/2024)

* Fixes error in Metal3D processed download link ([#28](https://github.com/a-r-j/ProteinWorkshop/pull/28))
* Fixes typo in wandb run name setting ([#30](https://github.com/a-r-j/ProteinWorkshop/pull/30))
* Fixes paths for models and datasets when testing instantiation of each module ([#32](https://github.com/a-r-j/ProteinWorkshop/pull/32))
* Improvements to TFN, MACE and EGNN models and layers, including DiffDock-style intermediate edge feature creation (TFN), dropout, gaussian RBF, mean global pooling ([#38](https://github.com/a-r-j/ProteinWorkshop/pull/38))

### 0.2.3 (31/08/2023)

* Minor patch; adds missing `overwrite` attribute to `CATHDataModule`, `FoldClassificationDataModule` and `GeneOntologyDataModule`. ([#25](https://github.com/a-r-j/ProteinWorkshop/pull/25))


### 0.2.2 (30/08/2023)

* Fixes raw data download triggered by absence of PDB when using pre-processed datasets ([#24](https://github.com/a-r-j/ProteinWorkshop/pull/24))
* Fixes bug where batches created from `in_memory=True` data were not correctly formatted ([#24](https://github.com/a-r-j/ProteinWorkshop/pull/24))
* Consistently exposes the `overwrite` argument for datamodules to users ([#24](https://github.com/a-r-j/ProteinWorkshop/pull/24))
* Fixes bug where downloading FoldComp datasets into directories with the same name as the dataset throws an error ([#24](https://github.com/a-r-j/ProteinWorkshop/pull/24))
* Increments `graphein` dependency to `1.7.3` ([#24](https://github.com/a-r-j/ProteinWorkshop/pull/24))

### 0.2.1 (29/08/2023)

* Fixes incorrect lookup of `DATA_PATH` env var ([#19](https://github.com/a-r-j/ProteinWorkshop/pull/19))

### 0.2.0 - 28/08/2023

* First public release
