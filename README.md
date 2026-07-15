<h1 align="center">
  <font size="7" style="color: #2563eb;">Liva AI 🤖</font>
</h1>

<h2 align="center">
  <strong>Yapay Zeka Destekli YouTube Yorum Analiz Programı v7.1</strong>
</h2>

<h3>Liva AI - Detaylı Kullanım Rehberi</h3>

[Rehber Videosunu İzlemek için Tıkla!](https://youtu.be/EQgztO0zY48)

<hr>

## 🚀 Yeni Kayıt Otomasyonu (v7.1)

*   **📝 Entegre Kayıt Talebi Sistemi:** Giriş ekranına doğrudan entegre, şık bir kayıt paneli eklenmiştir. Başvurular doğrudan Firestore üzerinde izole bir havuzda toplanır.
*   **🌍 Esnek Uluslararası İletişim:** Telefon numarası formatı, yurt dışındaki (Almanya, Azerbaycan, İran vb.) tebliğ ekiplerinin de sisteme başvurabilmesi adına esnetilmiştir. Başında `+` işareti olan tüm uluslararası numaralar kabul edilir ve `wa.me` WhatsApp köprü yapısıyla %100 uyumlu çalışır.
*   **🎯 Kurşun Geçirmez Girdi ve Yaş Doğrulama Motoru:** Form gönderimi esnasında e-posta, telefon ve şifre güvenlik denetimleri eksiksiz yapılır. Doğum tarihi alanı hem takvim seçiminde hem de klavyeden elle girişlerde sahte veri girişleri otonom olarak engellenir. Not alanı isteğe bağlı hale getirilmiştir.
*   **🔐 Otomatik Üye Üretimi ve Akıllı Giriş Denetimi:** Yönetici panelinden bir başvuru onaylandığı an, kullanıcının verileriyle Firebase Authentication hesabı, Firestore rol tanımlamaları ve şifre kayıtları otomatik olarak oluşturulur. Başvurusu hala inceleme aşamasında olan kullanıcılar sisteme girmeye çalıştığında *"Kayıt talebiniz hala incelenmektedir..."* uyarısıyla karşılanır. Reddedilen talepler (❌) ise veritabanından güvenle temizlenir.
*   **💎 Kalıcı Üst Yönetim Yetkisi:** Üst yönetim yetkisi, sayfa yenilense bile tarayıcı yerel hafızasında (`localStorage`) kilitli kalır. Bu sayede yöneticinin sürekli şifre girme zorunluluğu ortadan kalkar. Yetki, yalnızca "Güvenli Çıkış" yapıldığında tamamen imha edilir.

<hr>

## 🔥 Öne Çıkan Yeni Özellikler (v7.0)

*   **🤖 %100 Otonom İş Akışı ve Bulut Veritabanı Entegrasyonu (Google Drive & Google Sheets):** Yapay zeka yorum analizi sistemi **TAMAMEN OTOMASYONA** dönüştürülmüştür. Analiz edilen tüm veriler ve onaylanan yorumların ekran görüntüleri Google Drive üzerinde hiyerarşik bir veritabanı gibi otomatik olarak klasörlenir. Aynı zamanda temizlenen ve filtreden geçen yorum verileri Google Sheets (E-Tablo) üzerindeki ana veritabanına otomatik olarak gönderilir. Tüm bu Drive klasörleme ve E-Tablo aktarım süreçleri, Yönetici Paneli'ndeki log kayıtları üzerinden tek tıkla dinamik olarak yönetilebilir ve silinebilir.
*   **🛡️ Gelişmiş Rol Bazlı Erişim Kontrolü (RBAC):** Sisteme "Üst Yönetim Şifresi" ve "Kullanıcı Panel İzni" mantığı getirildi. Artık "Ortak Yönetici Şifresi" kaldırıldı. Yöneticiler her şeyi kontrol ederken, izin verilen "Kullanıcılar" paneli sadece rehber (read-only) mantığında görebilir. İşlemler sütunu ve butonlar yetkisiz kişilerden otomatik olarak gizlenir.
*   **👥 Yönetici Panelinden Dinamik Yetkilendirme:** Ekip tablosu üzerinden kullanıcılara tek tıkla "Erişim İzni Ver / Kaldır" butonu eklendi.
*   **🧩 Modüler ve Esnek Ekip Ekleme Formu:** Ekip üyesi eklerken Ad Soyad, Telefon, E-posta, Şifre, Rol (Zorunlu) ve Doğum Tarihi, Ekip Adı, Sorumlu Olunan Diller, Panel İzni (İsteğe Bağlı) alanları ile detaylı profil oluşturma imkanı sağlandı. Tablo üzerinden bu bilgilerin tamamı (kalem ikonu ✏️ ile) güncellenebilir hale getirildi.
*   **🔒 İkincil Onay Kalkanı (Re-Authentication):** Ekip üyesi silme veya rol değiştirme gibi kritik işlemlerde, kullanıcının kendi hesap şifresini canlı olarak Firebase sunucularında doğrulaması sağlandı. Veritabanına (Firestore) dışarıdan müdahale edilmesini engelleyen katı güvenlik kuralları (Security Rules) yazıldı.
*   **⏳ Otonom Tarih Çakışması Kontrol Motoru (Senaryo A & B):** Kullanıcının analiz etmek istediği tarih aralığı, veritabanındaki geçmiş analiz kayıtlarıyla karşılaştırılarak veri kaybı veya mükerrer token harcaması önlenir. Çakışma durumunda sistem kullanıcıya otomatik tarih düzeltme teklifi sunar (Senaryo A: Mükerrer Analiz, Senaryo B: Veri Kaybı).
*   **📅 Dinamik Tarih Seçim Arayüzü:** Akıllı Otomatik ve Manuel tarih modu geçişleri modernize edildi. Gelecek (henüz yaşanmamış) zaman seçimi, tarayıcı takvim arayüzü (min/max özellikleri) ve anlık JavaScript denetimleriyle engellendi.

<hr>

## 🌟 Eski Sürümdeki Mevcut Özellikler (v6.0)

* **Kusursuz Video Türü Ayrımı (%100 Doğruluk):** Sistem artık YouTube Data API'nin resmi sistem playlist yapılarını (`UUSH` ve `UULF`) kullanarak Shorts ve Uzun videoları sıfır hata ve maksimum hızla ayrıştırır
* **🗂️ Toplu Yorum Analizi Modu (Bulk Processing):** Kanal tarama ekranında tek seferde birden fazla video seçerek ardışık analiz başlatabilirsiniz. Sistem tüm videoları sırayla işler, raporları ayrı ayrı üretir ve tek bir `.zip` arşivi olarak bilgisayarınıza indirir.
* **🔒 Gelişmiş Yönetici Paneli (Admin Dashboard):** Veritabanı (Firestore) üzerinden şifre doğrulamalı, tüm ekibin indirme hareketlerini izleyebileceğiniz ve "Daha Önce Analiz Edildi" rozetlerini tek tıkla sıfırlayabileceğiniz merkezi yönetim alanı eklenmiştir.
* **📊 Akıllı Kullanıcı Bazlı RPD Tüketim Özeti:** Ekip üyelerinin Gemini API kotalarını nasıl harcadığını canlı takip eden; Bugün, Son 7 Gün ve Toplam harcanan RPD miktarını anlık hesaplayan analitik özet tablosu panele entegre edilmiştir.
* **👥 Güvenli Ekip Yönetimi, Telefon No ve Düzenleme:** Admin paneli üzerinden ekip üyelerine Ad Soyad, Telefon ve Rol atayabilir, kalem (✏️) butonuyla bilgileri düzenleyebilir veya tek tıkla yetkilerini kalıcı olarak iptal edebilirsiniz.
* **🛡️ Otonom Güvenlik Duvarı:** Ekip listesinden silinen veya yetkisi düşürülen bir kullanıcı, tarayıcı sekmelerini açık bıraksa bile herhangi bir işlem butonuna bastığı an güvenlik kontrolüne takılır, sistem yetkilerinin sonlandırıldığını anlar ve kullanıcıyı otomatik olarak dışarı atar.
* **🏷️ Akıllı Durum Rozetleri ve Emojiler:** Karışık listeleme modunda videoların yanına otomatik olarak `📱 Shorts` veya `🖥️ Uzun Video` rozetleri basılır. Ayrıca daha önce işlenen videoların yanında beliren `✅ Daha Önce Analiz Edildi` rozeti ekip içi mükerrer çalışmayı tamamen engeller.
* **✨ Livâü'l-Hamd Favicon:** Uygulamaya harici dosya bağımlılığı olmadan doğrudan koda gömülü, altın renkli şık bir "L" monogram favicon yerleştirilmiştir.

<hr>
Bu proje, YouTube içerik üreticilerinin ve tebliğ ekiplerinin videolara gelen on binlerce yorumu tek tıkla çekip, otonom yapay zeka mimarisiyle analiz ettirebilmesi için geliştirilmiş sunucusuz (serverless) bir web uygulamasıdır. 

Eski sürümlerde veriler yapay zekaya manuel olarak beslenirken; v5.0 ile birlikte sistem kendi içindeki **Gemini AI** motorunu kullanarak yorumları okur, sınıflandırır, özetler ve doğrudan hazır bir Excel tablosu olarak sunar.

<img width="647" height="484" alt="image" src="https://github.com/user-attachments/assets/eae45d25-67fe-4036-8c06-7c095422df28" />

## 🌟 Eski Sürümdeki Mevcut Özellikler (v5.0)

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
