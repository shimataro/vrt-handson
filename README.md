# [高火力 VRT](https://cloud.sakura.ad.jp/lp/vrt/) ハンズオン

さくらインターネットのGPUクラウドサービス「高火力 VRT」のハンズオンです。

## 必要なもの

- [さくらのクラウド](https://cloud.sakura.ad.jp/)のログイン情報（「会員ID」または「ユーザコード＆会員ID」）

## 事前準備

ハンズオンの前に、以下の準備が必要です。

1. [さくらのクラウド](https://cloud.sakura.ad.jp/)にログイン
1. [サーバ一覧](https://secure.sakura.ad.jp/cloud/iaas/#!/server/list/)からサーバーを追加
    - ゾーンは必ず「石狩第1ゾーン」を選択してください。
    - 「高火力 VRT(GPU)プラン」を選択してください。
    - モデルやチェックポイントのサイズが大きいので、ディスクサイズは多め（500GB以上）を選択してください。
1. サーバー起動後、[CUDA ToolkitとNVIDIA Driverをインストール](https://developer.nvidia.com/cuda-downloads)
    - `nvidia-smi` コマンドを実行して、正常にインストールされたことを確認してください。
1. このリポジトリーをサーバー上でclone

    ```bash
    git clone https://github.com/shimataro/vrt-handson.git
    ```

### Dockerを使う場合

ハンズオン内でDockerを使う場合は、追加で以下のセットアップが必要です。

- DockerおよびDocker Composeのインストール（以下のどちらかの方法で）
    - [Docker公式](https://docs.docker.com/desktop/setup/install/linux/)からインストール
    - Linuxディストリビューションのパッケージからインストール（Ubuntuの場合は `sudo apt install docker-compose` ）
- [NVIDIA Container Toolkitのインストール](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html)

### 一時領域について

H100には、高速・大容量の一時領域が付属しています。
詳しくは、マニュアルの[一時領域のご利用について](https://manual.sakura.ad.jp/cloud/server/gpu-plan.html#id7)を参照ください。

再起動でデータが失われるためご注意ください。

## ハンズオン一覧

以下のハンズオンでは、なるべく手軽に動かせるように手順を最小限にしています。
そのため、実際のサービス構築に必要なHTTPS・負荷分散・各種セキュリティーなどについては省略しています。

**くれぐれも、このまま本番運用しないようにお願いします。**

- [Open WebUIでLLM](./openwebui/README.md)
