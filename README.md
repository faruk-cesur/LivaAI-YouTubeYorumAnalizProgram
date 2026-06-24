<h1 align="center">
  <font size="7" style="color: #2563eb;">Liva AI 🤖</font>
</h1>

<h3 align="center">
  <strong>Yapay Zeka Destekli YouTube Yorum Analiz Programı v5.0</strong>
</h3>

<hr>


Bu proje, YouTube içerik üreticilerinin ve tebliğ ekiplerinin videolara gelen on binlerce yorumu tek tıkla çekip, **otonom yapay zeka mimarisiyle** analiz ettirebilmesi için geliştirilmiş sunucusuz (serverless) bir web uygulamasıdır. 

Eski sürümlerde veriler yapay zekaya manuel olarak beslenirken; v5.0 ile birlikte sistem kendi içindeki **Gemini AI** motorunu kullanarak yorumları okur, sınıflandırır, özetler ve doğrudan hazır bir Excel tablosu olarak sunar.

<img width="647" height="484" alt="image" src="https://github.com/user-attachments/assets/eae45d25-67fe-4036-8c06-7c095422df28" />

## 🌟 Öne Çıkan Yeni Özellikler (v5.0)

* **🧠 Otonom Yapay Zeka (Cascade) Mimarisi:** API kotalarını korumak için sistem 3 aşamalı çalışır:
  * **Aşama 0 (JS Ön Filtre):** 4 kelimeden kısa basit övgüler (spam) tarayıcı RAM'inde sıfır maliyetle anında silinir. *(İhtida/şehadet bildiren kelimeler istisna olarak korunur).*
  * **Aşama 1 (Hızlı Ön Eleme):** Gemini modeli, kalan yorumları büyük paketler halinde tarayarak sadece din, şüphe, felsefe veya duygu barındıranların kimliğini (ID) seçer.
  * **Aşama 2 (Derin Analiz):** Sadece nitelikli yorumlar cerrah titizliğiyle incelenip 1. tekil şahıs ağzından ("Ben" diliyle) Türkçe özetlenerek kategorize edilir.
* **☁️ Firebase Bulut Senkronizasyonu (Cloud Sync):** Cihaz bağımsızlığı! Yetkili girişinden sonra girdiğiniz API anahtarları, özel prompt şablonlarınız ve kota kayıtlarınız buluta kaydedilir. Telefondan veya başka bilgisayardan girseniz bile tüm ayarlarınız geri yüklenir.
* **⏱️ Akıllı Kota (RPD) Yöneticisi:** Google'ın günlük ücretsiz istek limitlerine (RPD) takılmamak için seçtiğiniz modelin günlük kotasını anlık olarak hesaplar, arayüzde gösterir ve her gün saat 10:00'da kotaları otomatik sıfırlar.
* **🌍 Otomatik Çeviri Entegrasyonu:** Yorumlar hangi dilde yazılmış olursa olsun (Rusça, Arapça, İngilizce vb.), Excel çıktısına Google Translate (gtx) üzerinden anlık **%100 Türkçe Çevirisi** eklenir.
* **🛡️ Mükerrer Kayıt Engelleyici (Deduplication):** Yapay zekanın "halüsinasyon" görüp aynı yorumu iki kez listelemesi ihtimaline karşı analiz sonrasında tarih ve kullanıcı adı taraması yapılarak liste otomatik olarak teke düşürülür.
* **📋 Dinamik Prompt Şablonları:** Sisteme entegre gelen *11 Kriterli Teolojik Analiz* ve *Dini Sorular/Şüpheler (Cevap Hazırlama)* şablonlarını kullanabilir veya tamamen kendi özel analiz promptunuzu oluşturup kaydedebilirsiniz.

<img width="636" height="807" alt="image" src="https://github.com/user-attachments/assets/6e9ca67c-5bb9-467b-a382-df609ee95359" />

## ⚙️ Klasik ve Güçlü Özellikler

* **Çift Formatlı Dışa Aktarım:** Verileri istatistiksel analiz için yapay zeka destekli Excel (`.xlsx`), geleneksel semantik LLM analizi için hiyerarşik Metin Belgesi (`.txt`) formatında indirebilirsiniz.
* **İki Farklı Çalışma Modu:**
  * **Tekil Video Modu:** Direkt link ile hedef videonun yorumlarını indirip analiz eder.
  * **Kanal Tarama Modu:** Hedef kanalın yüklediği tüm videoları (Yeniden Eskiye, Eskiden Yeniye veya En Popüler) listeleyip istatistiklerini görebilirsiniz.
* **Alt Yanıt (Reply) Mimarisi:** Ana yorumlara gelen alt yanıtları, sohbet akışını bozmadan ve LLM mantığına uygun şekilde hiyerarşik bağlarla çeker.
* **Taban Beğeni Filtresi:** Sadece belirli bir beğeni sayısına (Örn: +5 Beğeni) ulaşan nitelikli yorumları filtreleyebilme imkanı.

<img width="650" height="906" alt="image" src="https://github.com/user-attachments/assets/260cbc87-73f6-4eb8-b26f-6ec12b5cfab6" />

## 🚀 Kurulum ve Kullanım

Bu aracı kullanmak için ekstra bir kurulum yapmanıza (Node.js, Python vb.) gerek bulunmuyor.

* **1.** Google AI Studio üzerinde Gemini API anahtarı (API Key) oluşturuyoruz:
  * Siteye Git: Google AI Studio platformuna [Google AI Studio](https://aistudio.google.com/) bağlantısına tıklayarak doğrudan ulaşabilirsiniz.
  * Giriş Yap: Google hesabınızla oturum açın.
  * Anahtar Bölümüne Geç: Sol alt menüdeki "Get API key" (API anahtarı al) butonuna tıklayın.
  * Oluşturma Ekranını Aç: Açılan sayfada "Create API key" (API anahtarı oluştur) butonuna basın.
  * Proje Seç: "Create project" tıklayarak yeni bir proje oluşturun.
  * Anahtarı Kopyala: Ekranda görünen benzersiz API anahtarınızı kopyalayın.
* **2.** Bu bağlantı adresinden web uygulamasını açıyoruz: [YouTube Comment Downloader](https://faruk-cesur.github.io/YouTubeCommentDownloader/)
* **3.** Firebase güvenliği sayesinde yalnızca yetkilendirilmiş ekip üyesi e-posta ve şifresiyle **Giriş Yapıyoruz**.
* **4.** Yapay zeka modülünü kullanmak için **Kişisel Gemini API** anahtarımızı giriyoruz. (Sistem ping atmadan akıllı filtreleme ile hesabınızdaki çalışan aktif modelleri anında tarayıp listeler).
* **5.** İstediğimiz modeli, analiz şablonunu ve video linkini belirleyip süreci başlatıyoruz.
* **6.** Canlı "Tahmini Süre" ve "Kalan Yorum" sayacını takip ederek işlemin bitmesini bekliyor ve Excel dosyamızı alıyoruz.

> **💡 Güvenlik Notu:** API anahtarınız ve şablonlarınız Firebase Firestore üzerinde sadece size ait güvenli bir dökümanda saklanır ve üçüncü şahıslarla paylaşılmaz.

## 🤖 Klasik RAG Mimarisi (.txt Uyumluluğu)

Eğer yerleşik Gemini motoru yerine kendi özel modellerinizi (ChatGPT, Claude) kullanmak isterseniz, yapay zeka onay kutusunu kapatıp yorumları `.txt` olarak indirebilirsiniz. Alt yorumları farklı satırlarda gör işaretlendiğinde, programın ürettiği çıktı şu şekildedir:

```text
(28.08.2025 - 15:13) - [👍 977 Beğeni] - @KullaniciAdi : Yorum metni...
(05.12.2026 - 09:25) - [👍 651 Beğeni] - @DigerKullanici : Diğer yorum...

```

## 🛠️ Kullanılan Teknolojiler

* **Arayüz (UI):** HTML5, CSS3 (Modern Flexbox)
* **Mantık & Veri İşleme:** Vanilla JavaScript (ES6 Modules, Asenkron Fetch API)
* **Backend & Kimlik Doğrulama:** Firebase Firestore, Firebase Authentication
* **Yapay Zeka & API'ler:** Google Generative AI API (Gemini), Google Translate API (gtx), YouTube Data API v3
* **Veri Formatlama:** SheetJS (Excel .xlsx dışa aktarımı için)

## 👨‍💻 Geliştirici

**Faruk Cesur** bu projeyi geliştirmiştir. Projeye katkıda bulunmak veya iletişim kurmak için [Livâü'l-Hamd Instagram adresi](https://www.instagram.com/livaulhamd.official/) üzerinden iletişime geçebilirsiniz.

---

*Bu yazılım, dijital mecralardaki bilgi kirliliğini temizleyerek hakikati arayan insanlara ulaşmayı kolaylaştırmak gayesiyle geliştirilmiştir.*
