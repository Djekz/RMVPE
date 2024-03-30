# RMVPE
## 1. Training
The dataset consists of a mixture of processed mir1k and ptdb data, along with synthesized data from the m4singer vocoder, all standardized to 10ms per frame.

Place the training set in the `Hybrid/train` directory.

Place the test set in the `Hybrid/test` directory.

The `wav` files and `pv` files should be in the same directory.

Execute training:
```bash
python train.py 
```
Modify training parameters in the file as needed.

## 2. Visualization
```bash
tensorboard --logdir=runs
```
## 3. Testing
```bash
# See usage
python main.py -h 
```

## 4. Export
Exporting the model to ONNX format requires PyTorch nightly (>=2.1.0), otherwise the aten::stft operator cannot be exported.

Additionally, due to current limitations in PyTorch, the hop_length parameter must be static, meaning an ONNX model can only have one hop_length.

```bash
# See usage
python export.py -h
```
