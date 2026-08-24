<h1 align="center">
  <font size="7" style="color: #2563eb;">Liva AI 🤖</font>
</h1>

<h2 align="center">
  <strong>Yapay Zeka Destekli YouTube Yorum Analiz Programı (v10.0)</strong>
</h2>

<h2 align="center">
  <a href="https://youtu.be/EQgztO0zY48">
    <img src="https://img.shields.io/badge/REHBER_VİDEOSUNU_İZLE-FF0000?style=flat-square&logo=youtube&logoColor=white" width="300">
  </a>
</h2>

<hr>

Bu proje, YouTube içerik üreticilerinin ve tebliğ ekiplerinin videolara gelen on binlerce yorumu tek tıkla çekip, otonom yapay zeka mimarisiyle analiz ettirebilmesi için geliştirilmiş sunucusuz (serverless) bir web uygulamasıdır. 

Sistem, kendi içindeki **Gemini AI** motorunu kullanarak yorumları okur, sınıflandırır, özetler ve doğrudan Google Drive ile entegre çalışarak hazır bir Excel tablosu olarak sunar.

<table border="0">
  <tr>
    <td>
      <img width="640" alt="Liva AI - Arayüz 1" src="https://github.com/user-attachments/assets/e05b7ab3-683f-4acb-9315-29dfe1a7b1b4" />
    </td>
    <td>
      <img width="700" alt="Liva AI - Arayüz 2" src="https://github.com/user-attachments/assets/6708931e-5f09-4a07-9115-5e95fb097156" />
    </td>
  </tr>
</table>

<br>
<hr>

## ✨ Temel ve Güçlü Özellikler

*   **🧠 Otonom Yapay Zeka (Cascade) Mimarisi:** API kotalarını korumak için sistem 3 aşamalı çalışır. Gereksiz yorumlar RAM üzerinde maliyetsizce elenir; nitelikli, teolojik, felsefi veya dini şüphe barındıran yorumlar cerrah titizliğiyle incelenip 1. tekil şahıs ("Ben") diliyle Türkçe özetlenir.
*   **🤖 %100 Otonom İş Akışı ve Bulut Entegrasyonu:** Onaylanan yorumların ekran görüntüleri Google Drive üzerinde otomatik klasörlenir. Temizlenen veriler Google Sheets (E-Tablo) üzerindeki ana veritabanına otomatik aktarılır.
*   **🗂️ Toplu Yorum Analizi (Bulk Processing):** Kanal tarama ekranında birden fazla video seçerek ardışık analiz başlatılabilir. Sistem tüm videoları sırayla işler ve raporları ayrı ayrı üretir.
*   **🛡️ Gelişmiş Rol Bazlı Erişim Kontrolü (RBAC):** "Üst Yönetim Şifresi" ile yöneticiler tüm bulut süreçlerini kontrol ederken, izni olmayan kullanıcılar paneli sadece "Salt Okunur" (Read-only) modunda görüntüleyebilir. Yönetici Panelinden tek tıkla dinamik yetkilendirme yapılabilir.
*   **⏱️ Akıllı Kota (RPD) Yöneticisi:** Google'ın günlük ücretsiz istek limitlerine takılmamak için seçtiğiniz modelin kotasını anlık hesaplar. Tüketim özetleri Günlük ve Toplam bazda Admin panelinden takip edilebilir.
*   **🌍 Otomatik Çeviri & Dil Desteği:** Hangi dilde yazılmış olursa olsun (Arapça, Rusça, İngilizce vb.) yorumlara Google Translate (gtx) üzerinden anlık %100 Türkçe çeviri eklenir.

## 🚀 Kurulum ve Kullanım

Bu aracı kullanmak için bilgisayarınıza ekstra bir yazılım (Node.js, Python vb.) kurmanıza gerek yoktur.

1.  **API Anahtarı Alın:** [Google AI Studio](https://aistudio.google.com/)'ya giriş yapın. Sol menüden "Get API key" sekmesine geçip yeni bir proje üzerinden benzersiz Gemini API anahtarınızı oluşturun ve kopyalayın.
2.  **Sisteme Giriş Yapın:** [Liva AI - YouTube Yorum Analiz Programı](https://faruk-cesur.github.io/LivaAI-YouTubeYorumAnalizProgram/) adresinden uygulamayı açın.
3.  **Yetkilendirme:** Firebase güvenliği kalkanından geçmek için ekip e-posta ve şifrenizle giriş yapın. Yeni üyeyseniz giriş ekranındaki "Kayıt Talebi" formunu doldurarak onay bekleyin.
4.  **Analizi Başlatın:** Kişisel Gemini API anahtarınızı girin. İstediğiniz analiz şablonunu (ör. *11 Kriterli Teolojik Analiz*) ve hedef video linkini belirleyerek süreci başlatın.
5.  **Sonuçları Alın:** Canlı ilerleme çubuğunu takip edin. İşlem bitiminde Excel dosyanız cihazınıza inecek ve tüm kayıtlar bulut veritabanına işlenecektir.

> **💡 Güvenlik Notu:** API anahtarınız ve özel şablonlarınız Firebase Firestore üzerinde sadece size ait güvenli bir belgede şifrelenerek saklanır, kesinlikle üçüncü şahıslarla paylaşılmaz.

<img width="600" alt="giriş ekranı" src="https://github.com/user-attachments/assets/284f0c3b-ac2b-4ccc-b07c-0920944debea" />

<br>
<hr>

## 🎉 Liva AI - Güncelleme Notları (v10.0)

- **⚡ Yerel Yorumlar Veritabanı (Anında Erişim):** "Yorumlar Veritabanı" artık tarayıcınıza indirilip yerel olarak saklanabiliyor. Onay verdiğinizde ilk girişte tüm kayıtlar bir kere indirilir; sonraki girişlerde sistem sadece **yeni eklenen farkı** çeker. Sonuç: binlerce kayıtlık tablo, sunucudan tekrar tekrar beklemeden, göz açıp kapayana kadar önünüzde.
- **📊 Kullanıcı Bazlı Yapay Zeka Analiz Özeti:** Yönetici panelinde artık her ekip üyesinin bugün, son 1 hafta, son 1 ay, son 1 yıl ve toplamda kaç analiz yaptığını gösteren yepyeni bir özet tablo bulunuyor.
- **🧠 3 Kademeli Akıllı Otomatik Sıralama:** Kanal tarama ekranına "Sıralama: Akıllı Otomatik" seçeneği eklendi. Sistem videoları önce hiç analiz edilmemişlere, sonra kısmen tamamlananlara, en son da tamamlanmışlara göre önceliklendirerek sizi doğrudan iş yapılması gereken videoya yönlendiriyor.
- **➕ Son Analizden Beri Gelen Yorum Rozeti:** Daha önce analiz edilmiş bir videoya yeni yorumlar geldiyse, video kartında artık "kaç gün önce, kaç yeni yorum geldi" bilgisini gösteren bir rozet beliriyor. Hangi videonun güncellenmeyi beklediğini tek bakışta görün.
- **🙈 "Daha Önce Analiz Edilenleri Gizle" Modu:** Kanal listesinde tek tıkla, zaten analiz ettiğiniz videoları gizleyip sadece bekleyen içeriklere odaklanabilirsiniz.
- **🗑️ Toplu ve Tekli Log Silme:** Log kayıtları tablosuna, seçtiğiniz kayıtları topluca silebileceğiniz yeni bir mod ile her satırın yanına tek tıkla silme butonu eklendi.
- **🔍 Genişletilmiş Log Filtreleri:** Log kayıtları artık "Tarih Ayarı" (Akıllı Otomatik / Manuel) ve "İşlem Açıklaması" (Analiz Yapıldı, Manuel, Sonuç Yok, İndirildi, Durduruldu vb.) kriterlerine göre de filtrelenebiliyor; aktif filtre sayısı ekranda ayrıca gösteriliyor.
- **⌨️ Enter Tuşuyla Arama:** Yorumlar Veritabanında arama yaparken artık "Filtrele" butonuna basmaya gerek yok, sadece Enter'a basmanız yeterli.
- **🛡️ Yarım Kalan İşlem Uyarısı:** Bekleyen (yarıda kalmış) bir analiziniz varken sistem, üzerine yeni bir işlem başlatıp verilerinizin ezilmesini artık otomatik olarak engelliyor ve sizi doğru akışa yönlendiriyor.
- **🏷️ Video Kartlarında Zenginleştirilmiş Etiketler:** Videolarınızın yükleme sırası (#) ve yayın tarihi bilgisi artık kart üzerinde doğrudan görünüyor.
- **📥 İndirme Durumu Bildirimleri:** "Yorumlar Veritabanı" arka planda indirilirken üst çubukta ilerlemeyi takip edebilir, işlem bitince net bir onay mesajı görebilirsiniz.
- **🧹 Yorumlar Veritabanı Yönetim Kontrolleri:** Senkronizasyonu tamamen kapatıp yerel verileri temizleme, tabloyu manuel yenileme ve filtre alanlarını işlem sürerken geçici olarak kilitleme gibi ince ayar kontrolleri eklendi.
- **🚀 Daha Akıcı Arayüz Performansı:** Tekrar eden görsel testler ve gereksiz yeniden çizimler önbelleğe alınarak arayüzün takılmadan çalışması sağlandı.

---

## 🕘 Geçmiş Sürüm Notları

<details>
<summary><b>Geçmiş Sürüm Notları (v5.0 - v9.0) Göster / Gizle</b></summary>

*   **(v9.0) Yorumlar Veritabanı ve Akıllı Çeviri:** Yönetim paneline eklenen "Yorumlar Veritabanını Aç" butonu ile tüm analiz işlemlerinin tek tabloda incelenmesi. Yapay zeka ile hassas Türkçe çeviri, hızlı kategori düzenleme, gelişmiş log filtreleri ve akıllı sayfalama.
*   **(v8.1) Gelişmiş Model Yönetimi ve Arayüz İyileştirmeleri:** Yenilenen inceleme ekranı, akıllı model yönetimi ve log kayıtlarında model takibi.
*   **(v8.0) Kesintisiz Mimari ve Bulut Güvenliği:** Yorum resimleri ve analiz dosyaları arka planda önce RAM'de hazırlanır, ardından Google'a adım adım yüklenir. "Kaldığın Yerden Devam Et" (Akıllı İlerleme Kaydı) özelliği ile tarayıcı kapansa bile ilerleme kaybolmaz. Otomatik bulut temizliği, eklenti (adblock) kalkanı, anlık ağ kopmalarına karşı 3 kez tekrar deneme zırhı ve Firestore sunucu saatine kilitlenmiş manipülasyon korumalı RPD takibi eklendi. 
*   **(v7.2) Ekran Görselleri Optimizasyonu:** Ekran görselleri oluşturulurken karşılaşılan bir hata çözüldü ve sistem optimize edildi.
*   **(v7.1) Kayıt Otomasyonu:** Entegre kayıt talebi formu, uluslararası telefon numarası (wa.me) uyumluluğu, kurşun geçirmez yaş doğrulama motoru ve kalıcı üst yönetim yetkisi (localStorage).
*   **(v7.0) Rol Bazlı Otonomi:** RBAC ile dinamik ekip yetkilendirmesi, otonom tarih çakışması (Senaryo A & B) tespiti ve ikincil şifre doğrulama kalkanı (Re-Authentication).
*   **(v6.0) Toplu Analiz & Dashboard:** Merkezi Admin Dashboard, çoklu video (Bulk) işleme, kusursuz Shorts/Uzun Video ayrımı, akıllı kullanıcı bazlı RPD harcama istatistikleri.
*   **(v5.0) RAG Mimarisi:** Gemini entegrasyonu, 4 kelimelik spam ön filtre, mükerrer kayıt engelleyici ve dinamik prompt şablonları. ChatGPT veya Claude gibi harici modeller için `.txt` (Hiyerarşik Metin Belgesi) uyumluluğu.
</details>

<br>
<hr>

## 🛠️ Kullanılan Teknolojiler

*   **Arayüz (UI):** HTML5, CSS3 (Modern Flexbox ve Grid)
*   **Mantık & Veri İşleme:** Vanilla JavaScript (ES6 Modules, Asenkron Fetch API), IndexedDB (Yerel Veri Önbelleği)
*   **Backend & Kimlik Doğrulama:** Firebase Firestore, Firebase Authentication
*   **Yapay Zeka & API'ler:** Google Generative AI API (Gemini), Google Translate API (gtx), YouTube Data API v3
*   **Veri Formatlama:** SheetJS (Excel .xlsx dışa aktarımı için), html2canvas

## 👨‍💻 Geliştirici

**Faruk Cesur** bu projeyi geliştirmiştir. İletişime geçmek için [Livâü'l-Hamd Instagram adresi](https://www.instagram.com/livaulhamd.official/) üzerinden ulaşabilirsiniz.

<div align="center">
  <i>Bu yazılım, dijital mecralardaki bilgi kirliliğini temizleyerek hakikati arayan insanlara ulaşmayı kolaylaştırmak gayesiyle geliştirilmiştir.</i>
</div>
