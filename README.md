# 🚀 YouTube Yorum Yönetim Programı v3.1

Bu proje, YouTube içerik üreticilerinin ve veri analistlerinin, videolara gelen binlerce yorumu tek tıkla çekip, geniş dil modellerine (ChatGPT, Gemini, Claude vb.) analiz ettirebilmesi için geliştirilmiş sunucusuz (serverless) bir web aracıdır. Herhangi bir arka plan kurulumu (Node.js, Python vb.) gerektirmeden, doğrudan tarayıcı üzerinden çalışmaktadır.

<img width="824" height="490" alt="image" src="https://github.com/user-attachments/assets/bbde2fe5-eaca-4c25-b54f-ff423397fa82" />

## 🌟 Öne Çıkan Özellikler

* **Çift Formatlı Dışa Aktarım:** İhtiyaca göre verileri istatistiksel analiz için Excel (`.xlsx`), semantik yapay zeka analizi için hiyerarşik Metin Belgesi (`.txt`) formatında indirebiliyoruz.
* **Alt Yanıt (Reply) Mimarisi:** Ana yorumlara gelen alt yanıtları, sohbet akışını (eskiden yeniye) bozmadan ve LLM mantığına uygun şekilde `--->` bağımlılık işaretçileriyle çekiyoruz.
* **Taban Beğeni Filtresi:** Kısıtlı token kapasitelerini korumak adına, sadece belirli bir beğeni sayısına (Örn: +5 Beğeni) ulaşan nitelikli yorumları filtreleyebiliyoruz. Gereksiz ve düşük etkileşimli veriler otomatik olarak elenmektedir.
* **İki Farklı Çalışma Modu:**
  1. **Tekil Video Modu:** Direkt link ile hedef videonun yorumlarını indiriyoruz.
  2. **Kanal Tarama Modu:** Hedef kanalın yüklediği tüm videoları (Yeniden Eskiye, Eskiden Yeniye veya En Popüler sırasıyla) görsel bir liste halinde önizleyip istatistiklerini görebiliyoruz.
* **Akıllı Kota Yönetimi ve İptal Sistemi:** İşlem esnasında anlık ilerlemeyi (Progress Bar) takip edebilir, dilediğimiz an işlemi durdurup o ana kadar çekilen veriyi indirebiliyoruz.

<img width="654" height="913" alt="image" src="https://github.com/user-attachments/assets/7defa606-30ba-4d81-9ae7-179407d921e3" />

## ⚙️ Kurulum ve Kullanım

Bu aracı kullanmak için ekstra bir kurulum yapmamıza gerek bulunmuyor.

1. Aracı tarayıcıda açıyoruz (veya doğrudan GitHub Pages canlı linkine tıklıyoruz).
2. Karşılama ekranında **YouTube Data API v3** anahtarımızı giriyoruz. (Sistem, bu anahtarı arka planda Google Developers kanalına gizli bir istek atarak anında doğrulamaktadır).
3. Doğrulama başarılı olduğunda ana panele yönlendiriliyoruz.
4. Çıktı formatımızı, filtrelerimizi ve video linkini belirleyip indirme işlemini başlatıyoruz.

> **💡 Güvenlik Notu:** Girilen API anahtarı hiçbir sunucuya veya üçüncü taraf veritabanına gönderilmez. Doğrudan tarayıcınızın `localStorage` (Yerel Depolama) alanında şifrelenerek saklanır. Güvenli çıkış butonuna tıkladığınızda cihazınızdan tamamen silinir.

## 🤖 Yapay Zeka (LLM) Uyumluluğu ve RAG Mimarisi

Programın ürettiği `.txt` çıktısı, özellikle yapay zeka modellerine veri beslemek (Retrieval-Augmented Generation) için matematiksel bir düzende tasarlanmıştır. Çıktı formatı şu şekildedir:

```text
(28.08.2025 - 15:13) - [👍 977 Beğeni] - @KullaniciAdi : Ana yorum metni...
    ---> (29.08.2025 - 10:15) - @DigerKullanici : Ana yoruma verilen alt yanıt metni...
```

<img width="877" height="613" alt="image" src="https://github.com/user-attachments/assets/a696181c-4688-4810-9f8c-3084f5f53753" />

---

**Örnek LLM İstemi (Prompt):**
İndirdiğiniz metin belgesini yapay zekaya yükledikten sonra analiz için şu komutu kullanabilirsiniz:
*"Ekteki metin belgesinde YouTube izleyicilerimizin organik tartışmaları bulunmaktadır. `--->` ile başlayan satırlar, üstündeki ana yoruma verilen yanıtlardır. Lütfen izleyicilerin zihnindeki temel şüpheleri, en çok sorulan soruları analiz et ve bir sonraki video içeriğimiz için bu şüpheleri giderecek 3 farklı senaryo taslağı oluştur."*

## 🛠️ Kullanılan Teknolojiler

* **Arayüz (UI):** HTML5, CSS3 (Modern Flexbox)
* **Mantık & Veri Çekimi:** Vanilla JavaScript (ES6+, Fetch API, Asenkron Yapılar)
* **Veri Formatlama:** SheetJS (Excel .xlsx dışa aktarımı için)
* **Veri Sağlayıcı:** YouTube Data API v3

## 👨‍💻 Geliştirici

**Faruk Cesur**
Bu projeyi geliştirmek, katkıda bulunmak veya iletişim kurmak için [Livâü'l-Hamd Instagram adresi](https://www.instagram.com/livaulhamd.official/) üzerinden benimle iletişime geçebilirsiniz.

---

*Bu yazılım tamamen açık kaynaklıdır ve içerik üreticilerinin süreçlerini hızlandırmak amacıyla tasarlanmıştır.*
