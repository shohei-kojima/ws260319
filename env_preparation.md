# 2026/3/19 小嶋担当回 ハンズオン環境の構築

## 1. miniforgeのインストール
[こちらのセットアップガイド](https://github.com/juninamo/Bioinfo_lecture_Keio/blob/main/setup_guide_jp.md)の`1. コマンドライン（ターミナル）の使い方`と`2. Conda（Miniforge）のインストール`を参照し、Miniforge3をインストールします。


## 2. Conda環境の作成とソフトウェアのインストール

### Step A. Conda環境の作成
以下のコマンドを 1行ずつ ターミナル (macOS) または Miniforge Prompt (Windows) に入力して実行してください。

```
conda create -n ws260319 -c conda-forge r-base=4.5.2 python=3.10 -y
```

### Step B. 環境の有効化
```
conda activate scworkshop
```

### Step C. パッケージのインストール（conda経由）
```
conda install -c conda-forge r-ggplot2=4.0.2 -y
conda install -c bioconda bioconductor-deseq2=1.50.2 -y
conda install -c conda-forge seaborn=0.13.2 -y
conda install -c conda-forge scikit-learn=1.7.2 -y
conda install -c conda-forge notebook -y
conda install -c conda-forge r-irkernel -y
conda install -c bioconda pydeseq2
```

### Step D. jupyter notebookでpythonを使えるようにする
```
ipython kernel install --user --name ws260319
```


### Step E. jupyter notebookでRを使えるようにする
```
R  # これを入力するとRが起動するので、以下をRのコンソールに入力する

IRkernel::installspec(user = TRUE)
q()  # Rを終了
```


## データのダウンロード
[こちら](https://drive.google.com/drive/folders/10I3aYDWiSaxOxadoU083oYHCUUJQEwpF?usp=sharing)からどうぞ！  
慶應義塾のGoogleアカウントからのみダウンロードできます。  
以下の２つのファイルを手持ちのPCにダウンロードしてください。  
- count_matrix.tsv
- metadata.tsv


## 実習が終わったら
もし本環境が不要な場合、以下で環境を削除することができます。
```
conda remove --name ws260319 --all
```


