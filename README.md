# London Management Modern Web Projesi

Bu proje, eski Wix tabanlı altyapının yerini alarak Next.js, Tailwind CSS ve Framer Motion ile baştan aşağı yeniden tasarlanmış modern, premium ve animasyonlu bir web platformudur.

## 🚀 Kullanılan Teknolojiler

- **Next.js (App Router):** Hızlı, SEO uyumlu ve sunucu taraflı oluşturulan modern React framework'ü.
- **Tailwind CSS:** Özelleştirilebilir ve duyarlı tasarım için kullanıldı. Renk paleti siyah ve beyaz odaklı premium bir hisse sahip.
- **Framer Motion:** Sayfa geçişleri, global loader (yükleyici), kaydırma efektleri ve chat widget animasyonları için kullanıldı.
- **Prisma & PostgreSQL:** Veritabanı işlemleri için Prisma ORM kullanılmıştır. (Vercel'e kolay dağıtım için PostgreSQL uyumlu yapılandırılmıştır).
- **Recharts:** Admin panelinde ziyaretçi istatistiklerini görselleştirmek için eklenmiştir.

## ✨ Öne Çıkan Özellikler

1. **Çoklu Dil Desteği:** Sağ üstte yer alan bayraklı dil seçici ile İngilizce, Türkçe ve Almanca dilleri arasında geçiş yapılabilir. Seçimler çerezlerde (`js-cookie`) saklanır.
2. **Çerez Onay Paneli (Cookie Consent):** İlk kez giren ziyaretçilere zarif bir animasyonla çıkan ve onayı çerezlere kaydeden banner.
3. **Canlı Sohbet Widget'ı:** Kullanıcıların mesaj bırakabileceği sağ alt köşede yer alan animasyonlu sohbet balonu.
4. **Admin Dashboard:** `/admin` yolunda çalışan; site ziyaretçilerini gösteren bir grafik ve gönderilen son mesajların listelendiği gelişmiş bir panel.
5. **Global Yükleyici (Loader):** Sayfa ilk yüklendiğinde beliren şık açılış animasyonu.

## 📁 Proje Yapısı

```
├── prisma/
│   └── schema.prisma        # Veritabanı modelleri (Message, Visitor)
├── src/
│   ├── app/
│   │   ├── admin/           # Admin paneli ve grafikleri
│   │   ├── layout.tsx       # Ana yapı, Provider'lar ve Navbar
│   │   ├── page.tsx         # Modern, animasyonlu Ana Sayfa
│   │   └── globals.css      # Tailwind ayarları ve özelleştirilmiş scrollbar
│   ├── components/
│   │   ├── ChatWidget.tsx   # Canlı destek UI
│   │   ├── CookieBanner.tsx # Çerez onay paneli
│   │   ├── LanguageSwitcher.tsx # Bayraklı dil değiştirici
│   │   ├── Loader.tsx       # Başlangıç yükleyicisi
│   │   └── Navbar.tsx       # Üst menü
│   ├── context/
│   │   └── LanguageContext.tsx # Çoklu dil yönetimi (i18n state)
├── package.json             # Bağımlılıklar
└── tailwind.config.ts       # Tasarım ayarları
```

## ⚙️ Kurulum ve Çalıştırma

> **ÖNEMLİ:** Bu projeyi çalıştırabilmeniz için bilgisayarınızda [Node.js](https://nodejs.org/) kurulu olması gerekmektedir. Node.js kurulu olmadan `npm` ve `npx` komutları çalışmaz.

Node.js'i kurduktan sonra terminal (komut satırı) üzerinde bu klasöre (emirhan) gelerek sırasıyla şu adımları izleyin:

1. **Paketleri Yükleyin:**
   ```bash
   npm install
   ```

2. **Geliştirme Sunucusunu Başlatın:**
   ```bash
   npm run dev
   ```

3. **Tarayıcıda Görüntüleyin:**
   Tarayıcınızı açın ve `http://localhost:3000` adresine gidin.

## ☁️ Vercel ve Veritabanı Dağıtımı

Bu proje Vercel üzerine yüklenmek için hazırlandı. Veritabanı olarak **Vercel Postgres** kullanabilirsiniz.
- Vercel'de yeni bir Postgres veritabanı oluşturun.
- Size verilen `DATABASE_URL` bağlantısını Vercel proje ayarlarınızda "Environment Variables" kısmına ekleyin.
- Prisma tablolarını veritabanına göndermek için: `npx prisma db push`
