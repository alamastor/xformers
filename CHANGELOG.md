# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## TBD
### Fixed
- Updated triton dependency [#418]

### Added

## [0.0.12] - 2022-08-08
### Fixed
- Removed duplicated biases in the FusedMLP layers [#317]
- Rotary embeddings respecting input types [#326]
- Poolformer style instantiating useless projection layers [#349]
- Fix layer position not being properly tracked, causing extra layernorms for programmatic xformers [#348]
- Pass use_triton flag to LayerNorm module [#336]

### Added
- Four blocksparsity layouts from DeepSpeed [#320]
- Support several initialization options [#312]
- Conv2DFeedforward feedforward part [#321]
- VisualAttention [#329]
- Automatic blocksparse for causal attention [#334]
- Better hierarchical transformer generation [#345]
- Fused operations with AOTAutograd/NVFuser, integration into MLP [#357]
- Refactor LRA code to use Pytorch Lightning [#343]

## [0.0.11] - 2022-05-30
### Fixed
- Fix some torchscriptability [#246]
- Fix FourierMix being compatible with AMP [#258]
- Better asserts on QKV dimensions [#264]
- Better perfs for FusedMLP and FusedLinearLayer [#283]
- Deepnorm init missing self-attention [#284]

### Added
- Simplicial Embeddings [#259]
- Mem efficient attention, FW pass [#267]
- MHA benchmark
- MLP benchmark
- Move all triton kernels to triton v2 [#272]
- Mem efficient attention, BW pass [#281]
- Metaformer support [#294]

## [0.0.10] - 2022-03-14
### Fixed
- Expose bias flag for feedforwards, same default as Timm [#220]
- Update eps value for layernorm, same default as torch [#221]
- PreNorm bugfix, only one input was normalized [#233]
- Fix bug where embedding dimensions that did not match model dim would lead to a crash [#244]

### Added
- Add DeepNet (DeepNorm) residual path and init [#227]

## [0.0.9] - 2022-02-09
### Added
- Compositional Attention [#41]
- Experimental Ragged attention [#189]
- Mixture of Experts [#181]
- BlockSparseTensor [#202]
- Nd-tensor support for triton softmax [#210]

### Fixed
- Bugfix Favor, single feature map [#183]
- Sanity check blocksparse settings [#207]
- Fixed some picklability [#204]

## [0.0.8] - 2022-01-07
### Fixed
- Much faster fused dropout [#164]
- Fused dropout repeatability [#173]

### Added
- Embedding weight tying option [#172]

## [0.0.7] - 2021-11-30
### Fixed
- Dropout setting not properly passed in many attentions [#123]

## [0.0.6] - 2021-11-24
### Fixed
- Fix self attention optimization not being triggered, broken residual path [#119]
- Improve speed by not using contiguous Tensors when not needed [#119]

### Added
- Attention mask wrapper [#113]
- ViT comparison benchmark [#117]

## [0.0.4] - 2021-11-16
### Fixed
- Homogenizing the masks, additive or bool [#79][#85][#86]
- Fix causality flag not being respected [#103]
- Enabling FusedLayerNorm by default in the factory if Triton is available
- Fixing Favor with fp16
- Fixing Favor trainability

### Added
- Fused dropout/bias/activation layer [#58]
- Fused layernorm used by default in the factory [#92]


## [0.0.3] - 2021-11-01
### Fixed
- Nystrom causal attention [#75]


## [0.0.2] - 2021-11-01
### Fixed
- More robust blocksparse [#24]

### Added
- Rotary embeddings [#32]
- More flexible layernorm [#50]
