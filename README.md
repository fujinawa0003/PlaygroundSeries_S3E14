# PlaygroundSeries_S3E14
<img width="1199" alt="image" src="https://user-images.githubusercontent.com/88224359/236422276-25f2412f-be9d-4bdd-acd8-1c9cba436060.png">

# Dataset Description
The dataset for this competition (both train and test) was generated from a deep learning model trained on the Wild blueberry Yield Prediction Dataset. (Since this is Playground 3.14, it seems like we need a Blueberry Pie joke here?) Feature distributions are close to, but not exactly the same, as the original. Feel free to use the original dataset as part of this competition, both to explore differences as well as to see whether incorporating the original in training improves model performance.

このコンペティションのデータセット（trainとtestの両方）は、Wild blueberry Yield Prediction Datasetで訓練したディープラーニングモデルから生成されました。(Playground3.14なので、ここでブルーベリーパイのジョークが必要なような？) 特徴分布はオリジナルに近いですが、全く同じというわけではありません。このコンペティションでは、オリジナルデータセットを自由に使って、違いを探ったり、オリジナルをトレーニングに取り入れることでモデルの性能が向上するかどうかを確認したりすることができます。

Content
"The dataset used for predictive modeling was generated by the Wild Blueberry Pollination Simulation Model, which is an open-source, spatially-explicit computer simulation program that enables exploration of how various factors, including plant spatial arrangement, outcrossing and self-pollination, bee species compositions and weather conditions, in isolation and combination, affect pollination efficiency and yield of the wild blueberry agroecosystem. The simulation model has been validated by the field observation and experimental data collected in Maine USA and Canadian Maritimes during the last 30 years and now is a useful tool for hypothesis testing and theory development for wild blueberry pollination researches."

「予測モデリングに使用したデータセットは、ワイルドブルーベリー受粉シミュレーションモデルによって生成されました。このモデルは、植物の空間配置、交雑と自家受粉、蜂の種の構成、気象条件などの様々な要因が、単独または組み合わせで、ワイルドブルーベリー農業生態系の受粉効率と収量にどのように影響するかを探索できる、オープンソースの空間明示型コンピューターシミュレーションプログラムです。このシミュレーションモデルは、過去30年間に米国メイン州とカナダマリティーム州で収集された現地観察および実験データによって検証され、現在ではワイルドブルーベリーの受粉研究の仮説検証や理論構築に役立つツールとなっています。"

Features Unit Description
| Features | Unit | Description | 日本語 |
| --- | --- | --- | --- |
| Clonesize | m2 | The average blueberry clone size in the field | 畑のブルーベリークローンの平均サイズ |     
| Honeybee bees | m2| min Honeybee density in the field | 畑のミツバチ密度最小値 |    
| Bumbles bees| m2 | min Bumblebee density in the field | 畑のマルハナバチ密度最小値 |   
| Andrena bees| m2 | min Andrena bee density in the field | 畑のヒメハナバチ密度最小値 |      
| Osmia bees| m2 | min Osmia bee density in the field | 畑のオスミアバチ密度最小値 |    
| MaxOfUpperTRange | ℃ | The highest record of the upper band <br>daily air temperature during the bloom season | 開花期における上層帯日中の最高温度 |    
| MinOfUpperTRange | ℃ | The lowest record of the upper band <br>daily air temperature |  開花期における上層帯日中の最低温度 |    
| AverageOfUpperTRange | ℃ | The average of the upper band <br>daily air temperature | 上層帯日中平均気温 |    
| MaxOfLowerTRange | ℃ | The highest record of the lower band <br>daily air temperature | 下帯日中の最高温度|    
| MinOfLowerTRange | ℃ | The lowest record of the lower band <br>daily air temperature | 下帯日中の最低温度|    
| AverageOfLowerTRange | ℃ | The average of the lower band <br>daily air temperature | 下帯日中気温の平均温度|    
| RainingDays | Day | The total number of days during the bloom season,<br>each of which has precipitation larger than zero | 開花期において、降水量が0より大きい日の総日数|    
| AverageRainingDays | Day | The average of raining days of the entire<br>bloom season | 開花期全体の平均降雨日数|    

# Reference
| No | Status | Name | Detail | Url |
| --- | --- | --- | --- | --- |
| 01 | to do | 🍇Simple EDA and baseline in 2mintues! | voteが高いcode_1 | [url](https://www.kaggle.com/code/kimtaehun/simple-eda-and-baseline-in-2mintues)|
| 02 | to do | PS3E14 EDA_Various models & Ensemble baseline | vote及びscoreが高いcode_2 | [url](https://www.kaggle.com/code/tetsutani/ps3e14-eda-various-models-ensemble-baseline)|
| 03 | to do | EDA, FE, Models, Ensemble for Starters | voteが高いcode_3 | [url](https://www.kaggle.com/datasets/shashwatwork/wild-blueberry-yield-prediction-dataset)|
| 04 | to do | PS S3E14, 2023 EDA and Submission | voteが高いcode_4 | [url](https://www.kaggle.com/code/sergiosaharovskiy/ps-s3e14-2023-eda-and-submission)|
| 05 | to do | [PS S3E14, 2023] First place winning solution | 一位の解法 | [url](https://www.kaggle.com/code/sergiosaharovskiy/ps-s3e14-2023-first-place-winning-solution)|


# やってみたいことリスト
| No | Status | Name | Detail |
| --- | --- | --- | --- |
| 01| done | EDA | EDA|.  
| 02| done | LightGBM | LightGBMでのbaseline|
| 03| to do | reference04読む | XGBoostのbaseline |
| 04| to do |  | |


# Log
## 230520


## 230507
reference02を色々と読み、lightGBMの条件を見比べていったところ'objective'をregression_l1にすると格段にスコアが良くなる傾向であった。

## 230506
reference04を読んでみた。スコアは高かったが、そのスコアはXGBoostのものではなさそう。    

reference02を読んでみた。
概要としては色々なモデル（同じモデルであってもハイパーパラメータを変えているものも含む）を作り、   
それらのモデルの重みをoptunaで最適化している。    
正直よくわかっておらず、次にvoteの高いアンサンブルのスターターのcodeを読んでみる。    

reference03を読む。    
Adversarial Validation（敵対的バリデーション）を初めて知った。   
trainデータとtestデータの分布が異なっているかを確認する。    
trainのyeildをdropし、test dataにはラベルをつけ、このtestデータのラベルを分類できるかを確認する。    
今回のコードではtrainとtestではAUCがほぼ0.5であったため、trainとtestに差はほとんどないことがわかった。    
しかしoriginal dataでは0．７となっており、訓練データに含めない方が良さそうである。   
sns.kdeplotでカーネル密度を出すことができる。分布の可視化に有効。    
特にデータ数が異なる場合、ヒストグラムの縦が異なるためわかりにくくなるので、カーネル密度比較がいいと思われる。    
多重共線性が多いため、階層木でみるようだが、なぜ？

## 230505
feature engineeringで下記を作製した。  
```
join['total_bees'] = join['honeybee'] + join['bumbles'] + join['andrena'] + join['osmia']
join['range_of_upperT'] = join['MaxOfUpperTRange'] - join['MinOfUpperTRange']
join['range_of_lowerT'] = join['MaxOfLowerTRange'] - join['MinOfLowerTRange']
join['diff_aveupper_lower'] = join['AverageOfUpperTRange'] - join['AverageOfLowerTRange']
join['MaxOfUpperTRange*RainingDays'] = join['MaxOfUpperTRange'] * join['RainingDays']
join['MinOfLowerTRange*RainingDays'] = join['MinOfLowerTRange'] * join['RainingDays']
join['clonesize*total_bees'] = join['clonesize'] * join['total_bees']
```
ただしスコアは伸びなかった。

相関が強い。   
[MaxOfUpperTRange, MinOfUpperTRange, AverageOfUpperTRange,MaxOfLowerTRange, MinOfLowerTRange,AverageOfLowerTRange]   
[RainingDays, AverageRainingDays]

## 230504
EDAおよびlightGBMでbaselineを作製した。   
今回のEDAはplotlyを使ってinteractiveに作製。   
Public Score is 350.50063
今回のEDAはplotlyを使ってinteractiveに作製。   
