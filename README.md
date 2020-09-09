# twelve-step-os-docker

12ステップで作る組込みOS自作入門をdockerから動かすスクリプトです

`twos <「make image」など 元の実行コマンド>`のみでdocker特有の長いコマンドを書かずにビルドや書き込みを実行できます

初回実行時には、dockerイメージのビルド作業が入るため時間がかかります。

# 使い方

1. クローンしてきて`source myenv`
2. コンパイルしたい12ステップで作る組込みOS自作入門のコード上で`twos <「make image」など 元の実行コマンド>`

# 書き込みについて

書き込みたい場合は、書き込むデバイスを`TWOS_SERIAL_DEVICE=/dev/ttyUSB0 twos make write`のように指定して実行してください。