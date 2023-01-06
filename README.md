# QuantumEngineers_JC_DS_VL_07_FinalProject

# DC Residential Properties

Source:
[dataset](https://www.kaggle.com/datasets/christophercorrea/dc-residential-properties?select=DC_Properties.csv)

Outline:
* Business Problem
* Data Understanding
* Exploratory Data Analysis & Data Preprocessing
* Data Analysis
* Modeling
* Conclusion and Recommendation

## Business Problem

**Context**


Washington, D.C.(DC) adalah Ibu Kota dan juga pusat pemerintahan United States of America / Amerika Serikat.  [Berdasarkan sensus tahun 2020](https://opendata.dc.gov/), DC memiliki jumlah penduduk 689.545 dan memiliki jumlah tempat tinggal sebanyak 350.364 unit. Seperti yang kita tahu, pusat kota akan memiliki biaya hidup yang tinggi, dan properti merupakan aspek dalam biaya hidup, sehingga biaya properti di DC sangatlah tinggi.

Berdasarkan Federal Reserve Economic Data, rata-rata harga *single-family home* (rumah pribadi) di Washington, D.C. berada di kisaran 647.000 USD, sedangkan rata-rata harga rumah di Amerika Serikat pada tahun yang sama berada di kisaran 399.700 USD [(FRED, 2017)](https://fred.stlouisfed.org/series/ASPUS).  Namun, tingginya harga properti di DC tidak menurunkan konsistensi kota tersebut sebagai salah satu pasar properti yang diminati penduduk Amerika Serikat [(Atlaslane)](https://www.atlaslane.com/post/investment-property-washington-dc-best-areas#:~:text=Washington%2C%20DC%20is%20consistently%20ranked,month%20when%20rent%20is%20collected).  Dikarenakan demand yang tinggi dari penduduk Amerika Serikat, banyak perusahaan *real estate* seperti [The One Street](https://www.onestreet.one/), [GreenLine](https://www.greenlinere.com/), [Fulcrum Property](https://www.fulcrumproperty.com/), dan perusahaan lainnya yang memanfaatkan peluang ini, sehingga persaingan bisnis di bidang *residential real estate* menjadi sangat kompetitif. Untuk dapat bersaing, Residential Real Estate Company perlu memberikan layanan yang optimal antara lain dengan memberikan penawaran harga terbaik dan sesuai dengan segmentasi pasar.


Tingginya harga properti akan berdampak pada stabilitas ekonomi negara.  Misal, perumahan pribadi yang kita beli pada tahun 2006 akan tinggi harganya 5-10 tahun mendatang. Area komersil yang dibangun seperti apartment, area perkantoran, dan retail pun akan membantu stabilitas ekonomi negara.  Namun, jika hal ini tidak teregulasi dengan baik, akan menyebabkan bubble dimana kondisi harga properti terlalu tinggi tapi masyarakat tidak mampu membeli, dampaknya adalah harga properti akan jatuh dan juga stabilitas ekonomi akan goyang.[(TheBalanceMoney)](https://www.thebalancemoney.com/how-does-real-estate-affect-the-u-s-economy-3306018). 

Besarnya peran harga properti kepada stabilitas ekonomi Amerika Serikat, menyebabkan pemerintah juga turut menentukan dan mengatur kebijakan yang berdampak pada harga properti [(Fannie and Freddie)](https://www.chicagobooth.edu/review/should-government-intervene-housing-market). Sehingga untuk memberikan penawaran harga, kita perlu mengikuti kebijakan dan kualifikasi dari pemerintah. Selain mengikuti kebijakan pemerintah, survey terhadap properti residential juga perlu dilakukan untuk memperkirakan harga yang tepat. Namun, seperti yang dikutip dilaman Department of Consumer and Regulatory Affairs Washington, D.C., proses survey secara konvensional memakan biaya yang cukup besar, membutuhkan waktu yang cukup lama, dan berpotensi terjadinya *overpriced* dan *underpriced*, [(Angi)](https://www.angi.com/articles/how-much-does-land-survey-cost.htm).

Di sisi lain, perusahaan perlu mengetahui segmentasi properti residential atau commercial untuk diberikan ke target market yang sesuai sebagai penunjang Department Marketing perusahaan. Strategi marketing dengan cara menawarkan rumah secara acak tanpa memberikan batasan tertentu dapat memberikan hasil yang kurang efektif.  Maka dari itu dibutuhkan analisa seorang data scientist agar dapat memberikan insight yang akan berguna untuk menentukan harga yang tepat.

**Problem Statement**  
  
Penerapan metode survey untuk memperkirakan harga properti residential tidak efisien karena akan memakan waktu dan biaya yang lebih. Selain itu, subjektifitas dalam penentuan harga jual oleh surveyor tidak dapat dihindari, sehingga dapat menyebabkan terjadinya *overpriced* dan *underpriced*. *Overpriced* maupun *underpriced* dapat merugikan perusahaan. Kasus *overpriced* dapat menyebabkan properti tersebut sulit terjual karena harga yang kurang bersaing, sedangkan pada kasus *underpriced* dapat menyebabkan *profit loss* [(CPG)](https://www.durangohomesforsale.com/blog/what-to-know-about-overpricing-or-underpricing-your-home/).  Disamping itu, budget marketing akan menjadi tidak efisien jika perusahaan tidak mampu menentukan segmentasi properti dengan tepat. 


**Goals**  
  
Berdasarkan permasalahan diatas, tujuan analisa yang dilakukan adalah sebagai berikut :
1. Melakukan segmentasi properti untuk meningkatkan produktivitas Department Marketing
1. Memberikan prediksi harga properti residential dengan meminimalisir error sehingga tidak *overpriced* atau *underpriced*, dan mengurangi biaya dan waktu pengerjaan survey properti

Dengan menggunakan pemodelan machine learning, permasalahan di atas bisa diselesaikan dengan cara yang lebih efisien dibandingkan dengan cara konvensional sehingga kinerja perusahaan meningkat.

**Analytic Approach**   
   
1. Melakukan analisa data untuk dapat menemukan pola dari fitur-fitur yang ada. 
1. Melakukan pembuatan, evaluasi, dan implementasi model machine learning regresi sebagai *tool* yang dapat digunakan untuk memprediksi harga properti residential. 


**Metric**  
    
Evaluation metrics yang digunakan dalam model regresi adalah

- RMSE: akar rata-rata nilai kuadrat dari error
- MAE: rata-rata nilai absolut dari error
- MAPE: rata-rata persentase error
- R-Squared: koefisien determinasi yang mengindikasi besarnya kombinasi variabel independen mempengaruhi variabel dependen

MAE dan MAPE merupakan metrik yang tidak sensitif terhadap outlier. Semakin rendah nilai MAE dan MAPE maka semakin akurat model dalam prediksi harga properti residential. 

Selain itu R-squared merupakan koefisien determinasi yang mengindikasi besarnya kombinasi variabel independen mempengaruhi variabel dependen. Nilai R-squared berkisar diantara 0 dan 1, dimana semakin tinggi nilai R-square maka semakin baik model regresi. R-squared hanya bisa digunakan pada model linear.


##Conclusion

**Feature Importances**


* Berdasarkan pemodelan yang sudah dilakukan, fitur `GRADE`, `GBA`, dan `SALEYEAR` menjadi fitur yang paling berpengaruh terhadap `PRICE`.

* Fitur `GRADE` menunjukkan harga properti yang meningkat seiring dengan meningkatnya kualitas mutu properti. Properti dengan Grade Exceptional terbukti memiliki harga yang lebih tinggi daripada properti dengan Grade Good atau Fair.

* Fitur `GBA` menunjukkan luas bangunan yang mempengaruhi meningkatnya harga rumah. Semakin besar luas bangunan akan meningkatkan harga rumah.

* Fitur `SALEYEAR` merupakan fitur yang signifikan dalam pemodelan ini karena median harga properti yang naik seperti yang terlihat pada Data Analysis Price on Trend.

* Fitur `WARD` yang  sudah di-encoding dengan binary encoding memiliki feature importances yang tinggi untuk setiap fitur hasil encodingnya. Hal ini menunjukkan bahwa fitur `WARD` memiliki andil dalam menentukan harga properti. Seperti pada data analysis, Ward 2 dan Ward 3 memiliki median harga yang lebih tinggi daripada Ward lainnya sehingga properti baru di kedua Ward tersebut akan diprediksi memiliki harga yang lebih tinggi.



**Price Prediction** 

Metrik evaluasi yang digunakan pada model adalah nilai MAE, MAPE, dan R-Squared. Jika ditinjau dari nilai MAPE yang dihasilkan oleh model setelah dilakukan hyperparameter tuning, yaitu sebesar ~13%, kita dapat menyimpulkan bahwa bila nanti model yang kita buat ini digunakan untuk memperkirakan harga properti baru di Washington D.C. pada rentang nilai seperti yang dilatih terhadap model, maka perkiraan harganya rata-rata akan meleset kurang lebih sebesar 13% dari harga seharusnya.

Tetapi, tidak menutup kemungkinan juga prediksinya meleset lebih jauh karena bias yang dihasilkan model seperti yang terlihat dari visualisasi antara harga aktual dan prediksi.


1. Minimalisir Error

dari hasil diatas disimpulkan bahwa prediksi dengan XGBoost akan menghasilkan nilai error dengan rata-rata error +- 66,995 USD atau setara dengan 12,72% dari harga

Sehingga, perusahaan diharapkan dapat menentukan harga sesuai fitur properti dengan eror minimal dan mengurangi potensi *overpriced* atau *underpriced*.

Contoh sebelumnya pada tahap data understanding, kasus yang didapati adalah terjadinya *underpriced* (harga *underpriced* pada kolom `Unqualified` jika dibandingkan dengan kolom `Qualified` memiliki fitur yang hampir sama / identik) 

Jika contoh diatas dibandingkan dengan hasil permodelan maka perhitungan jumlah kerugian yang dapat dihindari sebagai berikut
- Sebelum permodelan = harga Qualified - harga Unqualified = 846,000 USD - 339,500 USD = 506,500 USD
- Setelah permodelan = MAE = 66,995 USD
Maka kerugian yang bisa diminimalisir adalah = 506,500 USD - 66,995 USD = 439,505 USD

2. Memotong Biaya Survey

Berdasarkan Business Problem, diketahui bahwa sebelum adanya permodelan, untuk mengetahui harga yang pantas / Qualified terhadap suatu properti, hal yang dilakukan adalah metode survey. Namun hal ini tidak efektif karena memakan biaya dan bersifat subjektif, maka dari itu dibuat model machine learning.

Menurut [angi](https://www.angi.com/articles/how-much-does-land-survey-cost.htm), harga average survey properti Washington D.C. berkisar di 450 USD per-survey. Oleh sebab itu harga tersebut akan digunakan sebagai perhitungan.

Pengeluaran biaya untuk jasa surveyor (asumsi, 1 orang surveyor = 40 jam kerja dalam 1 minggu [sumber](https://www.thebalancemoney.com/what-is-the-average-hours-per-week-worked-in-the-us-2060631):

- average price 1x survey = 450 USD
- waktu pengerjaan 1x survey = 40 jam / 5 hari = 8 jam/hari
- jika dalam 1 minggu terjadi 5 kali survey, maka dalam 1 tahun terjadi 5 * 52 minggu = 260 kali survey

total biaya survey / tahun = jumlah survey 1 tahun * biaya per-survey
> sum survey cost: 260 * 450 USD = 117,000 USD

Dengan bantuan Machine Learning, bila diasumsikan jasa surveyor tidak digunakan sama sekali, maka kita dapat menghemat biaya sebesar 117,000 USD/surveyor tiap tahunnya.

3. Maximal Allowance

Berdasarkan [investopedia](https://www.investopedia.com/terms/r/rentalreal-estate-loss-allowance.asp), maksimal allowance yang wajar untuk bisnis real estate adalah 20%. Dari analisis kami pada bagian model limitation, model yang kami buat dapat memenuhi batas allowance yang wajar untuk harga properti di atas 100,000 USD. 


##Recommendation

1. Model Recommendations:
  * Membuat pemodelan untuk properti berjenis Condominium sehingga bisa menjangkau prediksi harga seluruh properti di daerah Washington DC.
  * Melakukan tuning hyperparameter yang lebih banyak untuk meningkatkan performa model.
  * Menambahkan fitur lain seperti jarak ke public service, jumlah transportasi, dan lain sebagainya.
  * Menambah jumlah data khususnya pada range price di bawah 100.000 USD untuk memperoleh nilai MAPE yang lebih kecil.
  * Melakukan feature selection yang bisa meningkatkan performa model menjadi lebih signifikan seperti memanfaatkan hasil dari feature importance.
  * Melakukan pemodelan clustering untuk harga properti dengan machine learning seperti DBSCAN, Agglomerative Clustering, K-Means Clustering, dan lain sebagainya.

1. Business Recommendations
  * Meminimalisir kasus overpriced dan underpriced dengan menerapkan model machine learning yang telah dibuat untuk price prediction di masa yang mendatang.
  * Departemen Marketing dapat menggunakan model ini untuk menentukan waktu beli yang terbaik kepada customer.
  * Menerapkan model yang telah dibuat dalam sebuah aplikasi untuk memudahkan customer mengakses informasi dan memberikan promosi properti dengan harga yang paling tepat.
  * Menyediakan informasi segmentasi harga properti kepada departemen marketing untuk dapat menawarkan harga terbaik kepada target market yang sesuai
  * Menyediakan prediksi harga rumah dengan penambahan atau pengurangan fasilitas (fitur) dari properti yang diinginkan customer.

