# Pandas 基礎教學

## 簡報檔

簡報檔分享於 [Google Drive](https://drive.google.com/drive/folders/1ipVxxlkE2RZb-19yNiIBOH5vQHrZ6J2i?usp=sharing)。

## 需要用到的套件

### Python Dependencies

* [Jupyter Lab](https://github.com/jupyterlab/jupyterlab)：適合撰寫 Machine Learning 程式碼、觀察資料、以及妥善保存輸出內容的開發工具
* [Numpy](http://www.numpy.org)：高效能的數學函式庫
* [Pandas](https://pandas.pydata.org)：簡單易學的資料處理工具，也就是這次課程的重頭戲
* [Matplotlib](https://matplotlib.org)：資料視覺化工具，通常用來建立圖表
* [Scikit-learn](http://scikit-learn.org/stable)：Machine Learning 套件

#### 使用 `pip` 安裝

建議在[虛擬環境](https://docs.python.org/3/library/venv.html)底下操作：

```bash
$ pip install numpy pandas matplotlib scikit-learn graphviz jupyter jupyterlab
```

#### 使用 `conda` 安裝

```bash
$ conda install numpy pandas matplotlib scikit-learn graphviz jupyter jupyterlab
```

#### 使用 `pipenv` 安裝

```bash
$ pipenv install numpy pandas matplotlib scikit-learn graphviz
$ pipenv install jupyter jupyterlab --dev
$ pipenv lock --pre
```

### Graphviz

在我們的 Machine Learning 小範例中，有個步驟是畫出 Decision Tree，這時會用到這個可以繪製 DOT 語言的圖形的工具。

#### Ubuntu / Debian

```bash
$ apt-get install graphviz
```

#### CentOS / Fedora

```bash
$ yum install graphviz
```

#### Mac OS X / Mac OS

建議透過 [Homebrew](https://brew.sh) 安裝：

```bash
$ brew install graphviz
```

## 文件資料

### 上課教材

* [Python Pandas 基礎教學 iPython (Jupyter) Notebooks](https://github.com/VioletVivirand/pandas-tutorial)，其中包含幾個部分：
    * [`/Preprocessing`](https://github.com/VioletVivirand/pandas-tutorial/tree/master/Preprocessing): 用來處理上課用到的資料集的程式碼，客位可以參考看看原始資料長什麼樣子，而我們怎麼處理成 Machine Learning 分析時易於使用的資料格式，以及為什麼要這樣做
    * [`/Tutorials`](https://github.com/VioletVivirand/pandas-tutorial/tree/master/Tutorials): 每一個章節的主要課程內容，可以搭配簡報一起服用。但其中有幾個章節還未完成，我希望接下來會在有空閒的時候補完她們：
        * Chapter 0: 當初是為了幫 Python 基礎尚未打穩的同學做些常用的技法的重點提示，結果戰場開太多，不知道怎麼收斂，導致沒有寫完
        * Chapter 9: 包含了在做 Machine Learning 時，Feature Engineering 的一些手法，沒寫完的原因是不知道怎麼解釋得淺顯易懂，於是暫時擱著
    * [`/Practices`](https://github.com/VioletVivirand/pandas-tutorial/tree/master/Practices): 課堂習題。如果這次的課程來不及講，可以給各位當作測試自己有沒有學懂的一些小測驗
    * [`/Machine_Learning`](https://github.com/VioletVivirand/pandas-tutorial/tree/master/Machine_learning): 我們用 [Kaggle]() 上的 "Titanic: Machine Learning from Disaster" 入門競賽的資料及，做了一個 Machine Learning 的小小範例，讓大家看看 Pandas 處理完的資料可以這樣應用。但我們不會講得很深入，各位同學可以自行針對不懂的內容再行研究，或是期待下一堂講解 Machine Learning 的講師提供其他的指導～
* [上課簡報 (Google Drive)](https://drive.google.com/drive/folders/1ipVxxlkE2RZb-19yNiIBOH5vQHrZ6J2i?usp=sharing)

### 開發相關手冊與參考文件

* [Python 3 Docs](https://docs.python.org/3/)
* [Pandas](https://pandas.pydata.org)
    * [Docs](http://pandas.pydata.org/pandas-docs/stable/)
    * [10 Minutes to Pandas](http://pandas.pydata.org/pandas-docs/stable/10min.html)
* [Scikit-learn](http://scikit-learn.org/stable/)
    * [Docs](http://scikit-learn.org/stable/documentation.html)
    * [Choosing the right estimator](http://scikit-learn.org/stable/tutorial/machine_learning_map/index.html)
* [Matplotlib](https://matplotlib.org)
    * [Tutorials](https://matplotlib.org/tutorials/index.html)
    * [Docs](https://matplotlib.org/contents.html)
* [Seaborn](https://seaborn.pydata.org)
    * [Tutorial](https://seaborn.pydata.org/tutorial.html)
    * [Gallery](https://seaborn.pydata.org/examples/index.html)
* DevDocs
    * [Online Version](https://devdocs.io)
    * [Offline Version](https://devdocs.io/offline)
* Cheatsheets
    * [DataCamp](https://www.datacamp.com/community/data-science-cheatsheets)
        * [Python](http://datacamp-community.s3.amazonaws.com/50d31142-3de0-4159-89b9-18b718a728ef)
        * [Pandas](http://datacamp-community.s3.amazonaws.com/9f0f2ae1-8bd8-4302-a67b-e17f3059d9e8)
        * [Matplotlib](http://datacamp-community.s3.amazonaws.com/28b8210c-60cc-4f13-b0b4-5b4f2ad4790b)
        * [Seaborn](http://datacamp-community.s3.amazonaws.com/f9f06e72-519a-4722-9912-b5de742dbac4)
        * [Scikit-learn](http://datacamp-community.s3.amazonaws.com/5433fa18-9f43-44cc-b228-74672efcd116)
    * [Learn x in y minutes](https://learnxinyminutes.com)
