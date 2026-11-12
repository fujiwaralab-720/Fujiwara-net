# FujiwaraNet

本リポジトリには、擬似基板スペクトルを用いた深層学習エリプソメトリーに関する我々の研究において、基板汎化性能の評価（Fig. 3）に使用した薄膜材料のシミュレーションデータを収録している。本データは、当該評価で用いた材料および膜厚条件を記録する目的でのみ公開している。

---

## データの出典

薄膜材料の光学定数は、次に示す材料データベースを参照して作成した。

> H. Fujiwara and R. W. Collins (Eds.), *Spectroscopic Ellipsometry for Photovoltaics, Volume 2: Applications and Optical Data of Solar Cell Materials* (Springer, Cham, 2019).

各材料は、同データベースで用いられている誘電関数モデル（Tauc–Lorentz、Sellmeier、Tauc–Lorentz＋調和振動子）で表現し、データベースの材料分類に従ってフォルダごとに整理している。元データの著作権は原典に帰属する。

---

## ディレクトリ構成

```text
Fujiwaranet/
├── Organic(Tauc-Lorentz)/
├── Organic_Perovskites(Tauc-Lorentz)/
├── Semiconductor(Sellmeier)/
├── Semiconductor(Tauc-Lorentz)/
├── Semiconductor(Tauc-Lorentz+Harmonic Oscillator)/
├── Substrates-and-coating(Sellmeier)/
├── Substrates-and-coating(Tauc-Lorentz)/
├── TCO(Tauc-Lorentz)/
├── README.md
└── README-Japanese.md
```

各フォルダ名の括弧内は、収録した材料を表現する誘電関数モデルを示している。各フォルダには、材料ごとに1つの `*_nkd.csv` ファイルを収録しており、合計123ファイルである。

金属基板および SiO₂/Si 基板の評価には123材料すべてを使用し、透明基板の評価には透明薄膜材料を除いた107材料を使用した。

---

## ファイル形式：`*_nkd.csv`

| 列 | 内容 |
|---|---|
| `Energy` | 光子エネルギー（eV） |
| `n` | 屈折率 |
| `k` | 消衰係数 |
| `e1` | 誘電関数の実部 |
| `e2` | 誘電関数の虚部 |
| `ds_1`, `db_1`, …, `ds_6`, `db_6` | 評価に用いた表面粗さ層厚 $d_s$ とバルク層厚 $d_b$ の6通りの組み合わせ（nm） |

光学定数は、`Energy` 列に示す各光子エネルギーに対して行ごとに与えられている。6通りの膜厚の組み合わせは、1行目のデータ行にのみ記載している。膜厚は、$d_b$ = 10–300 nm、$d_s$ = 0–10 nm の範囲で材料ごとにランダムに選択した。
