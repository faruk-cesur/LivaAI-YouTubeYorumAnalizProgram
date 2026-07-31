<h1 align="center">
  <font size="7" style="color: #2563eb;">Liva AI 🤖</font>
</h1>

<h2 align="center">
  <strong>Yapay Zeka Destekli YouTube Yorum Analiz Programı (v9.0)</strong>
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

<br>
<hr>

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

## 🌟 v9.0 - Yorumlar Veritabanı ve Akıllı Çeviri (En Yeni Sürüm)

*   **🗂️ Yorumlar Veritabanı Merkezi:** Yönetim paneline eklenen "Yorumlar Veritabanını Aç" butonu ile yepyeni bir merkeze kavuştuk! Gerçekleştirilen tüm yapay zeka analiz işlemlerini tek bir tabloda inceleyebilir, geçmiş verileri detaylıca filtreleyebilir ve hatta bu eski verileri kendi içerisinde yapay zeka ile **tekrar analiz ederek** dilediğiniz spesifik içeriklere anında ulaşabilirsiniz.
*   **✨ Yapay Zeka ile Hassas Türkçe Çeviri:** Bazen Google Translate'in otomatik çevirilerinin kültürel veya teolojik anlamda yetersiz kalabildiğini fark ettik. Artık inceleme ekranında, yorumun hemen üstünde "✨ Yapay Zeka ile Türkçe'ye Çevir" butonu bulunuyor. Çeviriyi yetersiz bulduğunuzda bu butona basarak, metni yapay zekanın gücüyle kusursuz bir Türkçe'ye çevirtebilir ve tek tuşla eski çevirinin üzerine yazarak onaylayabilirsiniz.
*   **✏️ Hızlı Kategori Düzenleme:** Eğer incelediğiniz yorum değerliyse fakat atandığı kategori doğru değilse (veya daha uygun bir kategori varsa), artık "Düzenle" butonuna basarak o yorumun kategorisini işlem esnasında anında değiştirebilirsiniz.
*   **🔍 Gelişmiş Log Filtreleri ve Modern Arayüz:** Log kayıtları filtreleme paneli modern bir görünüme kavuşturuldu. Filtre seçenekleri artırılarak çok daha esnek bir arama altyapısı sunuldu. Ayrıca tablo ve menü başlıkları ekranın üstüne sabitlenerek kaydırma esnasında kaybolması engellendi.
*   **📊 Log Tablosunda Akıllı Sayfalama:** Binlerce log kaydının sistemi yormasını engellemek için tabloya "Sayfalama (Pagination)" özelliği eklendi. Artık kayıtlar çok daha hızlı ve sayfalar halinde düzenli yükleniyor. Ayrıca "Kullanılan Prompt" sütununa tıklanabilir bir **(👁️)** ikonu eklenerek, uzun komutların tamamını ekranı bozmadan tek tıkla okuyabilmeniz sağlandı.

<br>
<hr>

## 🛑 v8.1 - Gelişmiş Model Yönetimi ve Arayüz İyileştirmeleri 

*   **🎨 Yenilenen İnceleme Ekranı:** Yapay zekanın süzdüğü yorumları onayladığınız veya reddettiğiniz inceleme penceresinin tasarımı tamamen yenilendi. Sonuçları okumak ve kontrol etmek çok daha ferah, kolay ve göz yormayan bir yapıya kavuştu.
*   **⚙️ Akıllı Model Yönetimi ve Temiz Liste:** Kullanıcıların kafasını karıştıran, çalışmayan veya yorum analiziyle ilgisi olmayan gereksiz yapay zeka modelleri listeden tamamen temizlendi. Yöneticiler artık yeni çıkan modelleri yönetim paneli üzerinden tek tıkla sisteme çekip günlük limitlerini anında ayarlayabilecek.
*   **📊 Log Kayıtlarında Model Takibi:** Yöneticiler için log tablosu detaylandırıldı. Hangi videonun hangi yapay zeka sürümüyle (örneğin Gemini 3.5 Flash-Lite) analiz edildiği artık sistem loglarına otomatik olarak kaydediliyor.

<details>
<summary><b>Geçmiş Sürüm Notları (v5.0 - v8.0) Göster / Gizle</b></summary>

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
*   **Mantık & Veri İşleme:** Vanilla JavaScript (ES6 Modules, Asenkron Fetch API)
*   **Backend & Kimlik Doğrulama:** Firebase Firestore, Firebase Authentication
*   **Yapay Zeka & API'ler:** Google Generative AI API (Gemini), Google Translate API (gtx), YouTube Data API v3
*   **Veri Formatlama:** SheetJS (Excel .xlsx dışa aktarımı için), html2canvas

## 👨‍💻 Geliştirici

**Faruk Cesur** bu projeyi geliştirmiştir. İletişime geçmek için [Livâü'l-Hamd Instagram adresi](https://www.instagram.com/livaulhamd.official/) üzerinden ulaşabilirsiniz.

<div align="center">
  <i>Bu yazılım, dijital mecralardaki bilgi kirliliğini temizleyerek hakikati arayan insanlara ulaşmayı kolaylaştırmak gayesiyle geliştirilmiştir.</i>
</div>
