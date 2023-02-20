
# ***Bisnis Problem***
Daegu adalah kota terbesar ketiga di Korea Selatan setelah Seoul dan Busan, wilayah metropolitan terbesar ketiga di negara itu dengan populasi lebih dari 2,5 juta jiwa, dan kota terbesar kedua di wilayah Yeongnam di tenggara semenanjung Korea.

Daegu adalah pusat ekonomi Korea dari tahun 1960 hingga 1980-an dan terkenal dengan industri elektroniknya. Iklim subtropis yang lembap di Daegu ideal untuk menanam apel berkualitas tinggi, sehingga mendapat julukan "Kota Apel". Daegu juga dikenal sebagai "Kota Tekstil". Tekstil pernah menjadi industri terpenting di kota ini. Daegu saat ini berfokus pada fashion dan pengembangan industri teknologi tinggi.

Dengan pesatnya perkembangan Daegu, permintaan akan perumahan semakin meningkat. Kota Daegu akan memiliki 240.000 unit rumah pada tahun 2021.

Karena orang Korea sangat sibuk, mereka tidak punya cukup waktu untuk bertemu dengan calon pembeli, banyak pemilik unit apartemen yang mempercayakan transaksi penjualan kepada agen properti. Pentingnya penentuan nilai properti dapat membantu mempermudah transaksi jual beli properti. Menurut data Statista, jumlah properti di Kota Daegu yang belum terjual hingga tahun 2021 sebanyak 2000 properti.


Menurut Ruhl dan Ruhl Home Web, properti dengan harga yang wajar akan menarik calon pembeli. Semakin lama sebuah properti berada di pasar, semakin rendah nilai yang dirasakan dan kemungkinan akan dijual dengan harga lebih rendah. Oleh karena itu, diperlukan suatu alat bantu dalam suatu aplikasi untuk menentukan perkiraan harga suatu properti bagi agen properti.

Berdasarkan penelitian yang dilakukan oleh Onur Demirci, kelemahan Traditional Valuation dapat diatasi dengan melakukan advance valuation dengan model regressi machine learning. Dengan peningkatan volume transaksi dan perubahan pasar real estat, penilaian lanjutan (model pembelajaran mesin regresi) menjadi lebih dapat diterapkan.

Sehingga tools berupa model machine learning yang telah dibuat akan digunakan ketika pemilik unit apartemen ingin menjual unit apartemen melalui agen properti, maka agen properti akan memasukkan spesifikasi unit apartemen yang lalu akan mendapatkan prediksi harga unit apartemen yang akan dipasarkan. Dan saya sebagai machine learning engineer dari sebuah perusahaan property agent akan membuat dan maintain tools yang telah dibuat.

# ***Source***
Data dapat diambil melalui Kaggle ataupun melalui link https://drive.google.com/drive/folders/1fmkyfjrzuJNaH02sXhp5vUxqum9bH0Fx

# ***Modelling***

* KNN: adalah sebuah algoritma untuk melakukan klasifikasi terhadap objek dengan data pembe- lajaran yang jaraknya paling dekat dengan objek tersebut. Model ini diterapkan pada kasus yang sifatnya non parametrik.
* Decision Tree: adalah algoritma yang menggunakan seperangkat aturan untuk membuat keputusan dengan struktur seperti pohon yang memodelkan kemungkinan hasil, biaya sumber daya, utilitas dan kemungkinan konsekuensi atau resiko.
* Random Forest: Random Forest: adalah modifikasi dari metode begging, tujuannya juga sama yaitu membuat prediksi menjadi lebih stabil dan memperkecil ragam, perbedaanya dalam random forest kita akan memilih secara acak kandidat fitur yang akan digunakan dalam setiap splitting tree.
* Gradient Boosting: adalah algoritma yang memberikan model prediksi dalam bentuk ansambel model prediksi yang lemah.
* Lasso: model ini menggunakan regularizatio. Dengan mendorong model yang sederhana dan jarang (parameter lebih sedikit). Model ini sangat cocok untuk model yang menunjukkan tingkat multikolinieritas tinggi, maka dari itu model ini saya pertimbangkan juga mengingat adanya kasus mulikolinieritas pada tahap sebelumnya
* Ridge: adalah metode untuk memperkirakan koefisien model regresi berganda dalam skenario di mana variabel independen berkorelasi tinggi. Maka dari itu diharapkan model ini bisa menangani masalah multikolineritas.
* Adaboost: merupakan salah satu teknik ensamble dengan menggunakan loss function fungsi exponential untuk memperbaiki tingkat akurasi dari prediksi yang dibuat

# ***Metrics***

RMSE, dan R-SQUARE 
Pada dasarnya
 metrics ini saling berkaitan. Ketika kita kita memilih model menggunakan metrics ini. Model terbaik yang dihasilkan akan sama
persis. Perbedaan antara  metrics ini adalah pada interpretasinya. Misalnya pada MSE merupakan ragam dari residual, RMSE merupakan
standar deviasi dari residual dan R-Square yang menjelaskan seberapa besar variasi nilai Y yang dapat dijelaskan oleh model.
idealnya ketika kita gunakan mse nilai dari variabel Y tidak ada outlier sama sekali atau setidaknya hanya sedikit. Ketika
terdapat banyak outlier mse akan menjadi metrics yang kurang tepat untuk digunakan karen mse sangat sensitif terhadap outlier, maka dari itu kita tidak menggunakan MSE pada pekerjaan kali ini, selain itu juga karena mse sudah dapat dicerminkan melalui RMSE


Root Mean Square Error (RMSE) merupakan besarnya tingkat kesalahan hasil prediksi, dimana semakin kecil (mendekati 0) nilai RMSE maka hasil prediksi akan semakin akurat. Root Mean Squared Error (RMSE) merupakan salah satu cara untuk mengevaluasi model regresi linear dengan mengukur tingkat akurasi hasil perkiraan suatu model. RMSE dihitung dengan mengkuadratkan error (prediksi “ observasi) dibagi dengan jumlah data (= rata-rata), lalu diakarkan. RMSE tidak memiliki satuan. Root Mean Square Error merupakan salah satu kriteria dalam menentukan model peramalan selain MAPE, MAD dan MSE. Nilai RMSE rendah menunjukkan bahwa variasi nilai yang dihasilkan oleh suatu model prakiraan mendekati variasi nilai observasinya. RMSE menghitung seberapa berbedanya seperangkat nilai. Semakin kecil nilai RMSE, semakin dekat nilai yang diprediksi dan diamati.

MAE
Karena adanya residual yang tidak stabil, maka saya mempertimbangkan MAE untuk mengukur performance model kali ini, karena MAE merupakan alternatif dari MSE ketika kita banyak mendapati outlier pada residual. MAE merupakan metrics yang kurang
sensitif terhadap pencilan jika dibandingkan dengan MSE. MAE adalah agregat rata - rata error.

Selain itu MAE lebih mudah diinterpretasikan, hanya berupa rata - rata dari absolut error.

Sedangkan R-Square dianalogikan ketika kita makan mangga, tentu kita ingin memakan daging buah sebanyak - banyaknya.

MAPE
MAPE diperoleh dengan cara menghitung
residual dalam bentuk persentase. Setiap residual dibagi dengan nilai Y. Setelah itu kita absolutkan masing-masing residual lalu hitung
rata-ratanya. Metode ini digunakan ketika kita lebih tertarik untuk menghitung relative error dan ketika terlalu banyak outlier pada relative error

Berdasarkan **Lewis (1982)**, nilai MAPE dapat diinterpretasikan atau ditafsirkan ke dalam 4 kategori yaitu:

- lower than 10% = sangat akurat
- 10-20% = baik
- 20-50% = wajar
- higher than 50% = tidak akurat

Semakin kecil nilai MAPE maka semakin kecil kesalahan hasil pendugaan, sebaliknya semakin besar nilai MAPE maka semakin besar kesalahan hasil pendugaan. Hasil suatu metode pendugaan mempunyai kemampuan peramalan sangat baik jika nilai MAPE < 10% dan mempunyai kemampuan pendugaan baik jika nilai MAPE diantara 10% dan 20%.

# ***SHAPASH***
![image](https://user-images.githubusercontent.com/118766459/220081834-69f69c53-da0c-4e9b-861f-f23e4755544e.png)

# ***Kesimpulan***

Maka dari itu dapat kita simpulkan menjadi beberapa point penting:

1. Dataset ini cenderung lebih optimal dengan algoritma yang tree based serta boosting. Jika kita lihat berdasarkan MAE-nya, 4 performa terbaik ada pada Random Forest Regressor, Decision Tree Regressor, kemudian untuk yang boosting algorithm yaitu  Gradient Boosting.
Hal ini bisa disebabkan oleh beberapa faktor, dari yang saya baca dari https://www.summitllc.us/blog/advantages-of-tree-based-modeling , tree-based model ini cocok untuk dataset dengan berbagai tipe data, kita tahu bahwa dataset Daegu Apartments terdapat beberapa tipe data, yaitu numerikal dan kategorikal. 
Kemudian tree based model juga cocok untuk data yang sifatnya tidak terdistribusi normal. Selain itu Decision Tree juga dapat diterapkan pada data yang mengalami masalah non linieritas.
2. Jika dilihat dari nilai RMSE yang dihasilkan oleh model setelah dilakukan hyperparameter tuning, yaitu sebesar 48 USD per square feet, kita dapat menyimpulkan bahwa bila nanti model yang kita buat ini digunakan untuk memperkirakan harga apartemen baru di kota Daegu pada rentang nilai seperti yang di-training terhadap model, maka perkiraan harganya rata-rata akan meleset kurang lebih sebesar 48 USD per square feet dari harga yang mungkin seharusnya. Tetapi, tidak menutup kemungkinan juga prediksinya meleset lebih jauh karena bias yang dihasilkan model masih cukup tinggi pada harga prediksi yang semakin tinggi, seperti visualiasi yang telah ditunjukkan pada asumsi asumsi sebelumnya. 
Bisa dibuktikan juga pada pengujian model terhadap data test memiliki nilai yang meleset yang paling tinggi diatas 186 USD per square feet
 (diff). Hal ini terjadi karna adanya bias yang cukup tinggi pada model. 
3. Selain itu, jika kita lihat berdasarkan nilai MAPE, untuk hasil MAPE di bawah 20% dapat tergolong baik
4. Hasil dari Rsquare yang di atas 60% sudah cukup baik, artinya bahwa 60% variabilitas yang diamati dalam variabel target dapat dijelaskan oleh model regresi.
Ingat, bahwa R Square berfungsi untuk mengukur seberapa baik regresi merepresentasikan data.

![image](https://user-images.githubusercontent.com/118766459/220082190-6a5927df-334e-4276-b6dc-9849e0505c8c.png)

5. Dari hasil feature importance, umur suatu bangunan memiliki pengaruh yang signifikan, kemudian time to subway, lalu ukuran dari apartment. 
Hal ini cukup masuk akal, karena kemudahan akses transportasi juga menjadi nilai tambah ketika kita memilih tempat tinggal.
Lalu umur bangunan juga mungkin dapat berpengaruh pada harga, biasanya bangunan yang baru cenderung lebih kuat, bersih, dan biasanya secara design lebih modern (meskipun estetika sangat subjektif untuk diukur).
Yang terakhir yaitu Size, jika kita berkaca pada realitas, ukuran memang menjadi hal penting untuk mahal / murahnya sebuah tempat tinggal, bahkan di Indonesia sendiri sering menggunakan satuan per meter untuk mengkomunikasikan harga.
Lalu mengapa beberapa stasiun nilainya justru rendah? dugaan saya karena sebenarnya variabel tersebut sudah diwakilkan oleh time to subway, orang akan cenderung memperhatikan jarak/waktu ke stasiun terdekat daripada di mana stasiunnya, jika asumsinya seseorang memilih suatu apartment karena dekat dengan kantor, maka sebenarnya pertimbangan SubwayStation tidaklah terlalu penting, karena sehari-hari orang tersebut ke kantor dengan jalan kaki / kendaraan, bukan naik kereta. Kereta hanya digunakan saat menempuh perjalanan jauh. Namun perlu diingat kembali, ini adalah asumsi jika orang tersebut memilih suatu apartment karena dekat dengan tempat bekerjanya.

# ***Manfaat Bagi Bisnis***

Berdasarkan informasi yang saya baca dari https://hingemarketing.com/blog/story/cost_and_benefits_of_market_research , dengan Traditional Valuation, market researchers butuh waktu 2 - 8 minggu untuk melakukan riset harga terbaik dari satu apartment unit.

Sedangkan dengan Advance Valuation (machine learning model), kita dapat melakukan prediksi 1 unit apartment price kurang dari satu hari.

Anggaplah biaya market riset dalam 4 minggu adalah 100 USD per hari, jika dalam 4 minggu(dikurangi weekend / hari istirahat) maka total biayanya adalah 2000 USD. Jika dibandingkan dengan menggunakan ML yang hanya kurang dari 1 hari, maka perbandingannya adalah 100 USD : 2000 USD, atau lebih hemat 95 % (di luar estimasi biaya pengembangan ML). 

Apa artinya? secara tidak langsung kita bisa menurunkan biaya riset market, atau mengalihkannya untuk pengembangan ML. Tentunya akan berdampak juga untuk strategi marketing dari agen properti, karena bisa lebih cepat dalam menentukan harga, dan bisa menerapkannya pada berbagai bentuk, misalnya untuk bekerja sama dengan aplikasi jual beli apartment (travelio).

Selain itu dari sisi Buyer, dapat mereduksi resiko pembelian apartments dalam harga yang terlalu mahal
Dari sisi Penjual, akan bermanfaat dalam menentukan harga terbaik, supaya tidak terlalu mahal ataupun terlalu murah (sweet spot).

# ***Limitasi & Disadvantages***

1. Karena adanya penghapusan terhadap outlier, maka akan ada limit pada batas maksimal harga dan size yang dimasukan, untuk harga maximal yang bisa dimasukan adalah 510747.0, sedangkan size maximal yang bisa dimasukan adalah 1906.5
2. Pada fitur ageBuilding tidak dinamis / perlu diupdate kembali setiap ada pertambahan tahun. 
3. Karena kita menggunakan tree-based model, akan ada beberapa kekurangan,   
 - pertama, jika datanya terlalu besar (big data), maka akan terlalu banyak node yang terbuat, sehingga model menjadi terlalu kompleks dan overfitting. 
 - Selain itu terkait reusability-nya, karena perubahan kecil pada data (misal suatu saat ingin memasukan dataset yang serupa) dapat menyebabkan perubahan struktur secara signifikan (tree tidak stabil)
4. Masih sedikit bias seperti yang sudah dijelaskan pada Jika kita lihat dari grafik actual vs prediction, prediksi sudah merapat pada satu titik, namun ada sedikit kecenderungan untuk menyebar, terutama pada nilai di atas 200. Hal ini menandakan masih adanya potensi bias pada prediksi yang sudah dibuat, maka perlu menjadi concern ketika harga di atas 200 dollar per square feet, karena adanya potensi bias / kurang dapat dipercaya.


# ***Rekomendasi & Pengembangan***

REKOMENDASI PADA DATASET: 
 -  Tambahkan feature yang bisa menunjukan keunikan data sebagai primary key,  agar kita bisa memastikan bahwa tidak duplikat. Faktanya, data yang saat ini kita miliki tidak ada identifier-nya
 - Memperjelas beberapa feature, misalnya pada fitur jumlah fasilitas di dalam apartment, seharusnya digantikan dengan fitur lain yang lebih detil, misalnya kolam renang, gym, taman, biaya maintenance, dan sebagainya. Sehingga interpretasi juga akan lebih mudah.
 - Menambahkan fitur-fitur baru yang lebih korelatif dengan target (Sale Price), misalnya area perbelanjaan, jumlah tetangga, tingkat kriminalitas dan fitur-fitur lain yang mungkin dapat berpengaruh terhadap model.
 
REKOMENDASI TERHADAP BISNIS
 - Berhubung umur bangunan ternyata menjadi salah satu fitur yang penting, hal ini dapat dijadikan pertimbangan bagi pengembang /penjual apartment, namun umur bangunan tentu saja sifatnya fix / tidak bisa diubah, kecuali dirobohkan lalu dibangun lagi. Maka dari itu, bisa dilakukan renovasi secara teknis, kita juga bisa menambahkan fitur 'Latest Renovation' / kapan terakhir bangunan tersebut diperbaharui. Trade off-nya adalah biaya tambahan bagi pengembang, karena tentu saja melakukan renovasi tidaklah murah. Lalu apa solusi lainnya? kita bisa menggunakan strategi marketing yang lain, yaitu dengan lebih menekankan pada kelebihan lainnya (misalnya fasilitas, ukuran, ataupun transportasi terdekat), sehingga customer secara psikologis tidak terlalu memikirkan kapan apartemen tersebut dibangun, namun lebih tertarik kepada fitur yang sudah ditekankan oleh marketing.
  - Dengan adanya machine learning, maka proses riset terhadap harga tentu menjadi lebih cepat, maka kita bisa bekerja sama dengan aplikasi jual beli apartment (seperti travelio). Misalnya dengan memberikan rekomendasi harga pada pemilik apartment yang ingin menjual unit-nya. Contoh proses bisnisnya secara singkat, seller input data apartment/ spesifikasi apartment, kemudian aplikasi akan memunculkan rekomendasi harga jual. Sehingga seller pun tidak bingung dalam menentukan harga, tidak terlalu mahal dan tidak terlalu murah. Ke depan bisa dievaluasi, apakah dengan menerapkan model / rekomendasi tersebut traffic penjualannya semakin bagus? apakah akan lebih cepat terjual? Jika iya, berarti model tersebut berguna bagi bisnis. Maka hubungan antara Model Developer dan Aplikasi Jual Beli Properti bisa menjadi saling menguntungkan (misalnya dalam bentuk sharing profit)
REKOMENDASI TERHADAP MODEL
 - Alangkah baiknya juga model dapat mempertimbangkan juga dengan kota besar yang lain seperti Seoul dan Busan, karena wilayah geografis juga tergadang berpengaruh terhadap harga properti.
  - Pergunakan Grid Search, karena biasanya Grid Search juga dapat memeliki dampak pada performa secara lebih baik. Namun tentu ada trade off-nya, yaitu computational cost-nya, berarti membutuhkan device dengan spesifikasi yang baik.
  - Ada sebuah topik menarik, yaitu terkait House Price Bubble, terjadi ketika suatu harga properti naik secara signifikan dan kemudian harganya melambung turun drastis. Hal seperti ini bisa terjadi ketika harga properti terus naik tinggi sementara kapabilitas orang untuk membeli properti menurun (demand turun), atau mereka tidak ada kekuatan membeli (purchasing power). Di samping itu, ada sebuah pernyataan dari** Roberts, Lawrence (2008)**,
agar pasar otomatis bisa menyadari adanya price bubble
disarankan perubahan cara penilaian yang sudah ada yang 
menggunakan teknik sales comparison approach menjadi teknik income 
approach. Perubahan cara penilaian ini disebut oleh Roberts (2008) 
dengan sebutan market solution. Sales comparison approach didasarkan 
pada harga bangunan yang dianggap relative sama pada transaksi jual 
beli terakhir sehingga kenaikan harga suatu rumah memicu kenaikan 
harga rumah lainnya. Kemudian kita juga bisa mempertimbangkan income / penghasilan rata rata pada tiap daerah. Meskipun secara keuntungan berbisnis hal ini perlu diteliti lebih lanjut.
 - Gunakan algoritma lainnya, seperti deep learning, Recursive Neural Network, dll.
 - Buat GUI (Graphic User Interface) agar mempermudah user dalam memanfaatkan model ini, misalnya menggunakan Pickle yang dikombinasikan dengan StreamLit, dll.
 - Buat code menjadi lebih dinamis, misalnya pada umur bangunan bisa menyesuaikan tahun saat model tersebut dirunning (seperti fungsi Sysdate)
 - Jika konteks prediksi harga housing di Korea, akan lebih menarik bila dikontekstualisasikan dengan Krisis Korea tahun  1997 - 1998.
 - Model ini tentu masih dapat diimporvisasi agar dapat menghasilkan prediksi yang lebih baik lagi. Namun, kita dapat melakukan A/B testing terhadap model yang sudah dibuat pada project ini untuk mengetahui tingkat efektifitas penggunaan model.
 - Mengecek prediksi mana saja yang memiliki nilai error yang tinggi. Kita dapat mengelompokkan error tersebut ke dalam grup overestimation dan underestimation, lalu memilih 5% error paling ekstrim saja untuk tiap grup. Nantinya pengelompokkan akan menjadi 3 grup, yaitu overestimation (5%), underestimation (5%), dan grup mayoritas yang error-nya mendekati nilai mean (90%). Setelahnya kita bisa mengecek hubungan antara error tersebut dengan tiap variabel independen. Pada akhirnya kita dapat mengetahui sebenarnya variabel mana saja dan aspek apa yang menyebabkan model menghasilkan error yang tinggi, sehingga kita bisa melakukan training ulang dengan penerapan feature engineering lainnya.




