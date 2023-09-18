# FOSS4G 2023 Japan@FUKUI コアデイ 一般発表8
2023年9月18日（月）に福井市地域交流プラザにて開催されたFOSS4G 2023 Japan@FUKUI コアデイの一般発表8「[Segment Anything Modelを用いて地物抽出を試してみた](https://www.osgeo.jp/events/foss4g-2023/foss4g-2023-japan-at-fukui/foss4g-coreday#presentation8)」に使用した資料やデータ、Notebookを公開するためのリポジトリです。  

## 発表資料  
- [Googleスライド](https://docs.google.com/presentation/d/e/2PACX-1vRjK8Vtz9j05qFXay4uNSNfDt4JqnmazmUQFDjUWb6jphR_o5vw4AJP7NpuUjBobOaUQnXmoKObR_kq/pub?start=false&loop=false&delayms=3000)   

## 使用したデータ  
サンプルで使用したデータです。[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.ja)ライセンスで利用可です。

### リモートセンシング画像  

- [航空写真](./data/08NE1994.tif)
    + データの出典  
    静岡県「[VIRTUAL SHIZUOKA 静岡県 富士山南東部・伊豆東部 点群データ LPデータ　オルソ画像データ](https://www.geospatial.jp/ckan/dataset/shizuoka-2019-pointcloud/resource/b6f068b6-3d53-41e6-9f97-2f0c8833c786)  」 08NE1994  

- [光学衛星画像](./data/Sentinel2_Kirigamine.tif)   
    + データの出典
        + 20203/05/05に撮影されたSentinel-2衛星画像  
        + Google Earth Engineを用いて取得
        + 画像ID: COPERNICUS/S2_SR_HARMONIZED/20230505T013659_20230505T013655_T54STE  
        + 霧ヶ峰高原付近をクリップ  

### 3次元点群データ
容量の関係でLAZ形式に変換したデータを[こちら](./data/08NE3821.laz)からダウンロード可能です。  

- データの出典  
    静岡県「[VIRTUAL SHIZUOKA 静岡県 富士山南東部・伊豆東部 点群データ LPデータ　ダウンロードページ](https://www.geospatial.jp/ckan/dataset/shizuoka-2019-pointcloud/resource/d5e98a7b-f15c-45b0-bf40-0287f5b1de68)」 08NE3821  


## Notebook  
Google Colaboratory Proで動作確認をしています。  
- [segment_geospatial_googlecolab_example.ipynb](./segment_geospatial_googlecolab_example.ipynb)  
    [segment-geospatial](https://samgeo.gishub.org/)というPythonライブラリを用いて以下のことを行っているNotebookです。  
    + 航空写真に対して自動でのセグメンテーション、ポイントやテキストを用いた対象を指定してのセグメンテーション
    + 衛星画像を用いて山火事によって焼けた範囲を抽出するために、自動でのセグメンテーション、ポイントやバウンディングボックスを用いた対象を指定してのセグメンテーション

- [segment_lidar_googlecolab_example.ipynb](./segment_lidar_googlecolab_example.ipynb)  
    [segment-lidar](https://yarroudh.gitbook.io/segment-lidar)というPythonライブラリを用いて以下のことを行っているNotebookです。  
    + 3次元点群データを地物ごとにセグメンテーション  
