# posenet-body-on-tensorrt
posenet-body-on-tensorrt は、TensorRT 上で PoseNet Bodyの AIモデル を動作させるマイクロサービスです。  

## 動作環境

- PoseNet
- Docker
- TensorRT Runtime

## PoseNetについて
PoseNet Body は、主要な体の関節の位置を推定することにより、画像や動画内の人物のポーズを推定するAIモデルです。  
PoseNet Body は、特徴抽出にResNet18を使用してます。

## 動作手順
### Dockerコンテナの起動
Makefile に記載された以下のコマンドにより、PoseNet Bodyの Dockerコンテナ を起動します。
```
make docker-run
```
### ストリーミングの開始
以下のコマンドにより、TensorRT 上の PoseNet でストリーミングを開始します。  

```
build/aarch64/bin/posenet /dev/video0
```

## engineファイルについて
本レポジトリのengineファイルは、posenet-body-on-tensorrt/data/networks/Pose-ResNet18-Body/pose_resnet18_body.onnx.1.1.8001.GPU.FP16.engine にあります。  
なお、PoseNet Bodyの NVIDIA Jetson用の engineファイルは、[jetson-inference](https://github.com/dusty-nv/jetson-inference) からダウンロードできます。  



