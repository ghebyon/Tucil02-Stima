

<div id="top"></div>


<!-- PROJECT LOGO -->
<div align="center">
    <img src="images/Contoh.gif" alt="Logo">
  </a>

  <h2 align="center">Implementasi Convex Hull untuk Visualisasi Tes Linear Separability Dataset<br>dengan Algoritma Divide and Conquer<br><br></h2>

</div>

<!-- ABOUT THE PROJECT -->
## Tentang Project

Project berisi Library myConvexHull dalam bahasa Python yang dapat
mengembalikan convex hull dari kumpulan data 2 dimensi (dapat dianggap kumpulan
titik 2 dimensi). Himpunan titik pada bidang planar disebut convex jika untuk sembarang
dua titik pada bidang tersebut (misal p dan q), seluruh segmen garis yang berakhir di p
dan q berada pada himpunan tersebut. Kompleksitas rata-rata mencari Convex Hull dengan menggunakan algoritma Divide and Conquer adalah O(n*log(n)), sedangkan dalam kasus terburuk kompleksitas rata-ratanya adalah O(n^2)

Data set yang diimplementasikan :
<div align="center">
<table class="tg">

<tbody>
  <tr><td class="tg-0lax">Iris</td><td class="tg-0lax">https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_iris.html#sklearn.datasets.load_iris</tr>
  <tr><td class="tg-0lax">Digits</td><td class="tg-0lax">https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_digits.html#sklearn.datasets.load_digits</tr>
  <tr><td class="tg-0lax">Wine</td><td class="tg-0lax">https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html#sklearn.datasets.load_wine</tr>
  <tr><td class="tg-0lax">Breast Cancer</td><td class="tg-0lax">https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html#sklearn.datasets.load_breast_cancer</tr>
</tbody>
</table>
</div>

## Requirement

* python
* math
* numpy
* matplotlib
* pandas
* random
* sklearn

## Menjalankan Dataset yang lain 

1. Copy Paste bagian dibawah

    ```
    # Load Dataset
    data = datasets.load_<nama_data_set>() # diisi oleh nama data set
    df = pd.DataFrame(data.data, columns=data.feature_names)
    df['Target'] = pd.DataFrame(data.target)
    
    # Plot 
    plt.figure(figsize = (10, 6))
    plt.title('... vs ...') 
    plt.xlabel(data.feature_names[x]) # x diisi oleh salah satu index atribut
    plt.ylabel(data.feature_names[y]) # y diisi oleh salah satu index atribut
    for i in range(len(data.target_names)):
        bucket = df[df['Target'] == i]
        bucket = bucket.iloc[:,[x,y]].values # x dan y seperti yang diatas
        hull = myConvexHull(bucket)
        plt.scatter(hull.myPoints[:, 0], hull.myPoints[:, 1], label=data.target_names[i], color=colors[i])
        for simplex in hull.convexHullRelation:
            plt.plot(hull.myPoints[simplex, 0], hull.myPoints[simplex, 1], colors[i])
    plt.legend()
    ```
2. Run Program