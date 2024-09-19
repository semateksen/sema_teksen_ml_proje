# sema_teksen_ml_proje

Kaggle'daki notebook linkim:

https://www.kaggle.com/code/semateksen/sema-teksen-ml-proje/notebook

# No Show Appointments - Randevu Kaçırma Tahmini
## Proje Özeti
Bu proje, hastaların planlanan doktor randevularına katılıp katılmayacaklarını tahmin etmeyi amaçlamaktadır. Kaggle'dan alınan "No Show Appointments" veri seti kullanılarak, çeşitli makine öğrenmesi algoritmaları ile tahmin modelleri oluşturulmuştur. Projede kullanılan öğrenme türleri ve elde edilen sonuçlar analiz edilmiştir. Sonuçlar karşılaştırılarak hangi modelin daha iyi performans gösterdiği üzerine yorumlar yapılmıştır.

## Veri Seti
Veri seti, Brezilya'daki tıbbi randevulara ait bilgileri içerir ve hastaların randevuya katılıp katılmadığını gösteren bir hedef değişken (No-show) barındırmaktadır. Hedef değişkeni kullanarak, randevuya katılımı etkileyebilecek özniteliklerden (cinsiyet, yaş, randevu tarihi, hastanın tıbbi geçmişi vb.) yararlanarak tahmin yapılmaya çalışılmıştır.

### Kullanılan Özellikler
Gender: Hastanın cinsiyeti.
ScheduledDay: Randevunun planlandığı gün.
AppointmentDay: Randevunun olduğu gün.
Age: Hastanın yaşı.
Scholarship: Hastanın sosyal yardım alıp almadığı.
Hypertension: Hipertansiyon geçmişi.
Diabetes: Diyabet geçmişi.
Alcoholism: Alkol geçmişi.
Handcap: Engellilik durumu.
SMS_received: Hastaya randevu hatırlatma SMS'i gönderilip gönderilmediği.
No-show: Hastanın randevuya katılıp katılmadığı (Evet/Hayır).

## Projede Yapılanlar
1. Veri Ön İşleme:

Eksik veriler ve gereksiz sütunlar temizlendi.
Kategorik değişkenler (cinsiyet gibi) one-hot encoding ile sayısal verilere dönüştürüldü.
Yaş ve randevu gününe ait zaman verileri modelin eğitimi için uygun hale getirildi.

2. Veri Bölme:

Veri seti, %80 eğitim ve %20 test olacak şekilde bölündü.

3. Kullanılan Modeller: Aşağıdaki makine öğrenme algoritmaları ile modeller oluşturulmuş ve karşılaştırılmıştır:

Random Forest Classifier
Support Vector Machines (SVM)
Logistic Regression
K-Means Kümeleme (Gözetimsiz Model)

4. Hiperparametre Optimizasyonu:

Modellerin performansını artırmak için GridSearchCV ile hiperparametre optimizasyonu yapıldı.

5. Model Performans Karşılaştırması:

Modellerin performansı Accuracy (doğruluk), Precision (kesinlik), Recall (duyarlılık) ve F1 Skoru gibi metriklerle değerlendirildi.

## Kullanılan Kütüphaneler

Projede kullanılan Python kütüphaneleri şunlardır:

Pandas: Veri işleme ve analiz.
NumPy: Sayısal hesaplamalar.
Scikit-Learn (sklearn): Makine öğrenmesi algoritmaları ve veri ön işleme.
Matplotlib ve Seaborn: Veri görselleştirme.

## Sonuçlar
- Random Forest Classifier en yüksek doğruluk oranına sahipti ve genellikle en dengeli performansı gösterdi.
- Logistic Regression, Random Forest kadar olmasa da yaklaşık %75 doğruluk oranı ile başarılı bir sonuç verdi.
- Support Vector Machines (SVM) daha uzun eğitim süresi gerektirmesine rağmen, doğruluk oranı %72 ile diğer modellere kıyasla daha düşüktü.
- K-Means Kümeleme (gözetimsiz model) ise etiketi olmadan benzer örnekleri gruplandırmaya çalıştı, ancak etiketli tahmin modeli ile kıyaslandığında performansı yetersiz kaldı.

### Öğrenme Türleri Arasındaki Farklar
Gözetimli Öğrenme modelleri, etiketli veri ile çalıştıkları için hedef değişkeni başarıyla tahmin edebildi. Random Forest ve Logistic Regression en iyi performans gösteren modellerdi.
Gözetimsiz Öğrenme ise veri setinde hedef değişken olmadığı durumlar için uygundur. K-Means gibi algoritmalar, yalnızca veri kümeleri arasında benzerlikleri tespit edebildi ve tahmin yeteneği olmadığından gözetimli öğrenmeye göre zayıf bir performans sergiledi.

### Sonuçların Yorumlanması
Bu projede gözetimli öğrenme modellerinin daha başarılı olduğu görülmüştür. Random Forest, değişkenler arasındaki karmaşık ilişkileri daha iyi yakalayarak en iyi tahmin sonuçlarını verdi. Gözetimsiz öğrenme modelleri ise bu tarz etiketli veri setlerinde yetersiz kaldı.

##Kurulum
Projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki adımları takip edebilirsiniz:

1. Gerekli Python kütüphanelerini yükleyin:

pip install pandas numpy scikit-learn matplotlib seaborn
2. Veri setini indirin ve proje klasörünüze ekleyin.

3. notebook.ipynb dosyasını açın ve adım adım işlemleri takip ederek modeli eğitin ve test edin.
