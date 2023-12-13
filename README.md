# 量子大域変分学習による量子誤り訂正

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)


このリポジトリは、主に就活向けに自身の研究の概要を伝えるためのものである。学会及び論文ジャーナルに投稿予定につき、コードは掲載しない。

## 概要
量子コンピュータには、計算に使われるビットにノイズが入りやすいという実装課題があり、そのノイズを除去する技術が量子誤り訂正である。いくつかある手法の中で、量子コンピュータ上で自律的に量子誤り訂正できるように、量子機械学習を用いた手法が注目を集めている。本研究では、学習収束と高速化の点を従来より改善した新しい手法である量子大域変分学習を用いた量子誤り訂正について提案しその性能を評価した。

## 実行の様子
以下に実行の様子をgif化した動画像を掲載する。得られた２つの図の内、上方の図は学習過程におけるコスト関数の遷移である。下方は、３つの量子状態（提案手法で訂正、アルゴリズムで訂正、訂正前）に対して、正しい量子状態との忠実度を並べたものである。 <br><br>
![movie](/practice.gif) 

## 新規性・有用性
以下に出力として得られた図の一つと、学習についての計測値をまとめた表を掲載する。この図は、誤り率別の提案手法によって得られた忠実度と、アルゴリズム的な理論値としての忠実度の比較である。この図から、学習は問題なく行われており、精度も十分であることが分かる。また本研究では、従来手法と比較して、学習が正しく収束する確率の改善と高速化に成功しており、表にその結果をまとめた。<br><br>

![image](/fidelity_of_denoised_state_example.png)  <br>
|  | 提案手法 | 従来手法 |
| ----: | ----: | ----: |
| 学習収束確率[%] | 100 | 90 |
| 理論値に近い精度が得られる<br>までの学習時間平均[s] | 74 | 649 |

## 苦労した点
- 先行研究の具体的なコードが無く、先行研究の参考文献のコードから実装する必要があった点
- 上記コードがMATLABで記述されていたため、より効率的な機械学習の為にPythonで書き直した点
- 利用している計算上qiskitの回路に落とし込む事ができなかった点

## 展望
- ネットワーク内部でノイズが発生する場合の実装(実装済)
- 符号化手法の自律的な探索
- 隠れ層に厚みを持たせることでネットワーク内部でのノイズに耐性を持たせる

## 実装環境
- Ubuntu22.04
- Python 3.9.16

## 利用ライブラリ
- qiskit
- numpy
- matplotlib
