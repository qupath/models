# StarDist models

Here you can find pre-trained StarDist models as frozen *.pb* files that are compatible with OpenCV's DNN module.

This means they can be used in QuPath via the [QuPath StarDist extension](https://github.com/qupath/qupath-extension-stardist) without any requirement to install TensorFlow.

## Downloads

The converted model files are
* [dsb2018_heavy_augment.pb](https://github.com/qupath/models/raw/main/stardist/dsb2018_heavy_augment.pb) - single channel
* [dsb2018_paper.pb](https://github.com/qupath/models/raw/main/stardist/dsb2018_paper.pb) - single channel
* [he_heavy_augment.pb](https://github.com/qupath/models/raw/main/stardist/he_heavy_augment.pb) - RGB images


## Credit & reuse

The original models were trained by the StarDist developers, [Uwe Schmidt](https://github.com/uschmidt83) and [Martin Weigert](https://github.com/maweigert).

They are available from [https://github.com/stardist/stardist-imagej](https://github.com/stardist/stardist-imagej/tree/master/src/main/resources/models/2D) and the license file included here is from that repo.

The converted models here are made available under the same terms as a convenience; credit belongs to the original authors.

For more details, check out:

* [StarDist](https://github.com/stardist/stardist#pretrained-models-for-2d)
* [StarDist-ImageJ](https://github.com/stardist/stardist-imagej)

and also the source training data

* [DataScienceBowl 2018](https://bbbc.broadinstitute.org/BBBC038) ([CC0](https://creativecommons.org/publicdomain/zero/1.0/))
* [MoNuSeg 2018](https://monuseg.grand-challenge.org/Data/) ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode))
* [TNBC dataset from Naylor et al. 2018](https://doi.org/10.5281/zenodo.1174342) ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/legalcode))

## Conversion

Model conversion was performed using [tf2onnx](https://github.com/onnx/tensorflow-onnx)
```
python -m tf2onnx.convert --opset 10 --saved-model "/path/to/saved/model/" --output_frozen_graph "/path/to/output/model/file.pb"
```
