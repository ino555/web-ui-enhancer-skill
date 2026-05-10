---
name: web-ui-enhancer
description: >
  Statik web sitelerinin (HTML/CSS/JS) mevcut tasarımını analiz ederek modern, profesyonel ve
  akıcı bir görünüme kavuşturan skill. Kullanıcı bir HTML, CSS veya JS dosyası paylaşıp
  iyileştirme istediğinde, "daha güzel yap", "animasyon ekle", "modern görünüm", "tasarımı
  geliştir", "frontend iyileştir", "UI güncelle", "daha profesyonel yap", "daha iyi görünsün"
  gibi ifadeler kullandığında MUTLAKA bu skill'i kullan. Sayfanın amacına uygun renk tonları
  seçer — jenerik tech mavisinden kesinlikle kaçınır — ve CSS transitions, Intersection Observer
  gibi güncel animasyon teknikleri uygular. Mevcut kodu koruyarak yalnızca görsel ve etkileşim
  katmanını güçlendirir.
---

Bu skill statik web sitesi dosyalarını (HTML/CSS/JS) alır, mevcut tasarımı analiz eder ve
sayfanın **bağlamına, amacına ve hedef kitlesine** uygun özgün bir estetik yükseltme yapar.

---

## ⚠️ Birinci Kural: AI Klişelerinden Kaç

Her AI tool aynı tasarımı üretir. Sen farklı olacaksın. Şu kombinasyonlar yasaktır:

- ❌ Koyu arka plan (#0d0d0d, #0a0a0f) + mavi/mor gradient — "AI SaaS template"
- ❌ Glassmorphism + blur + neon glow — 2021'de modaydı, artık klişe
- ❌ Her site için benzer dark mode — bu bir portföy sitesi mi, kafe menüsü mü, hepsi aynı görünüyor
- ❌ #6c63ff, #2196f3, #7c3aed — bu renkler "AI tasarımı" demek
- ❌ Gradient blob arka plan + hero section aynı yapıda — her sitede var
- ❌ Tüm fontlarda Inter veya Roboto — sıkıcı

**Test:** Tasarladığın siteye baktığında "bu başka bir AI sitesine benziyor" diyebiliyor musun? Benziyorsa baştan yap.

---

## 1. Analiz Aşaması — Önce Anla, Sonra Tasarla

Kodu doğrudan değiştirme. Önce şunları çıkar:

**İçerik analizi:**
- Sayfa ne işe yarıyor? (e-ticaret, portföy, SaaS, blog, restoran, landing page…)
- Hedef kitle kim? (genç kullanıcı, kurumsal, yaratıcı sektör, teknik ekip, aileler…)
- Sayfanın tonu nedir? (ciddi, eğlenceli, minimal, güçlü, sıcak, cesur)
- İçerik ağırlığı ne? (metin yoğun mu, görsel mi, ürün mü, hizmet mi?)

**Kişilik belirleme:** Tasarlamadan önce siteye bir karakter ver:
> "Bu site [karakter gibi] hissettirmeli, [klişe] gibi değil."

Örnekler:
- Kafe → "Küçük Paris pastanesi, İtalyan espresso barı" — sıcak, davetkar, artisanal
- Portföy → "Vogue editörü, Pentagram tasarımcısı" — cesur, editorial, özgüvenli
- SaaS → "Linear, Vercel" — temiz, güvenilir, hızlı — ama AÇIK tema da olabilir!
- Startup → "Y Combinator demo day" — net, iddialı, odaklı

---

## 2. Renk Strateji — Özgün Ol

### Sayfa türüne göre başlangıç yönü:

| Sayfa Türü | Önerilen Yön | Özgün Seçenekler | Kesinlikle Kaçın |
|---|---|---|---|
| Restoran/Kafe | Sıcak ve artisanal | Espresso (#2c1a0e) + krem (#f5e6c8) + altın (#c8973a) | Tech mavileri, koyu monolit |
| Portföy (tasarımcı) | Editorial, cesur | Krem (#faf5ef) + siyah (#111) + tek canlı accent | Dark navy, gradient blur |
| Portföy (developer) | Clean ve odaklı | Beyaz + charcoal + yeşil (#16a34a) ya da turuncu | Mor-mavi gradient |
| SaaS/B2B | Güvenilir, temiz | **Açık tema**: beyaz + slate + tek vurgu rengi | Koyu+neon (clichè) |
| E-ticaret | Ürüne odaklı | Nötr zemin + ürün renkleri konuşsun | Her şeyi baskın renkler |
| Blog/içerik | Okunabilir | Krem/beyaz + koyu metin + tek accent | Renkli arka planlar |
| Eğitim/kurs | Profesyonel ama sıcak | Forest green (#166534) ya da navy + beyaz + amber | Çok canlı/oyunsu |
| Startup landing | İddialı, net | Güçlü kontrast, oversized tipografi | Purple-on-white klişesi |

### CSS custom properties — her rengi değişkene bağla:
```css
:root {
  --color-bg: #faf5ef;
  --color-surface: #ffffff;
  --color-accent: #c8973a;
  --color-text: #1a1008;
  --color-muted: #7a6a55;
  --color-divider: rgba(200, 151, 58, 0.25);
  --radius-sm: 6px;
  --radius-md: 14px;
  --transition-base: 220ms ease;
}
```

### Renk seçiminde özgünlük kuralı:
Standart palet tablolarından değil, sayfanın **duygusundan** çıkar:
- Kafe espresso barı → kahvenin rengi (#2c1a0e), kremanın rengi (#f5e6c8), buğdayın rengi (#d4a853)
- Organik ürün → yaprak (#2d5016), toprak (#8b4513), güneş (#e8c547)
- Lüks marka → siyah (#0a0a0a), altın (#c9a84c), beyaz (#fafafa) — minimalist, hiç gradient yok

---

## 3. Vizüel Modernlik — 2024-2025 Trendleri

Klişe tasarımdan kurtulmanın yolu doğru trendi kullanmak:

### Seçenekler (siteye uygun olanı seç, hepsini birden koyma):

**A) Oversized Tipografi** — en güçlü modernlik göstergesi
```css
.hero-title {
  font-size: clamp(3rem, 10vw, 8rem);
  font-weight: 800;
  line-height: 0.95;
  letter-spacing: -0.03em;
}
```
Büyük, cesur, az metin — güçlü bir mesaj. Portföy ve startup için idealdir.

**B) Bento Grid Layout** — kutu tabanlı, asimetrik
```css
.bento-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 200px;
  gap: 1rem;
}
.bento-item.large { grid-column: span 2; grid-row: span 2; }
```
Dashboard, portföy, özellik sayfaları için. Modern SaaS sitelerinde çok yaygın.

**C) Editorial Layout** — dergi/gazete hissi
Metin blokları farklı hizalarda, büyük boşluklar, kalın separator çizgiler.
Portföy ve blog için güçlü.

**D) Minimal + Animasyon** — az ama öz
Çok az renk, çok temiz layout, ama hover/scroll'da güzel micro-animations.
Her site için uygulanabilir.

**E) Texture/Noise** — düz renk yerine hafif doku
```css
.hero {
  background-color: var(--color-bg);
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
}
```
Düz renklere derinlik katar. Özellikle light theme'lerde etkili.

---

## 4. Animasyon Teknikleri

### Scroll-triggered reveal (temel, her sitede olsun):
```js
const observer = new IntersectionObserver((entries) => {
  entries.forEach(el => {
    if (el.isIntersecting) {
      el.target.classList.add('visible');
    }
  });
}, { threshold: 0.12 });
document.querySelectorAll('[data-reveal]').forEach(el => observer.observe(el));
```
```css
[data-reveal] {
  opacity: 0;
  transform: translateY(28px);
  transition: opacity 0.65s ease, transform 0.65s ease;
}
[data-reveal].visible { opacity: 1; transform: none; }
.card:nth-child(2)[data-reveal] { transition-delay: 80ms; }
.card:nth-child(3)[data-reveal] { transition-delay: 160ms; }
```

### Hover mikro-etkileşimler:
```css
.card {
  transition: transform 200ms ease, box-shadow 200ms ease;
  cursor: pointer;
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 32px rgba(0,0,0,0.12);
}
```

### Smooth scroll:
```css
html { scroll-behavior: smooth; }
```

### Floating header (scroll'da değişen):
```js
window.addEventListener('scroll', () => {
  document.querySelector('header').classList.toggle('scrolled', window.scrollY > 60);
});
```

---

## 5. Tipografi — Font Seçimi

Siteye kişilik katan doğru font kombinasyonu:

| Site Türü | Başlık Fontu | Gövde Fontu | His |
|---|---|---|---|
| Kafe/restoran | Playfair Display, Cormorant Garamond | DM Sans, Outfit | Sıcak, artisanal |
| Portföy (yaratıcı) | Syne, Cabinet Grotesk, Space Grotesk | Outfit, Plus Jakarta Sans | Cesur, modern |
| Portföy (developer) | JetBrains Mono (başlık), Inter | Inter, DM Sans | Teknik, temiz |
| SaaS/startup | Cal Sans, Manrope, Geist | Inter, DM Sans | Profesyonel, net |
| Editorial/blog | Libre Baskerville, Lora | Source Serif Pro, Georgia | Okuma odaklı |

**Font boyutu hiyerarşisi:**
```css
h1 { font-size: clamp(2.5rem, 6vw, 5rem); font-weight: 700; letter-spacing: -0.025em; }
h2 { font-size: clamp(1.75rem, 4vw, 3rem); font-weight: 600; }
h3 { font-size: 1.25rem; font-weight: 600; }
p  { font-size: 1rem; line-height: 1.7; }
```

---

## 6. Layout ve Boşluk

- **Padding tutarlılığı:** Tüm section'larda aynı yatay margin (örn: `max-width: 1200px; margin: 0 auto; padding: 0 2rem`)
- **Negatif boşluk kullan:** Dolu görünmek modern değil. Nefes aldır.
- **Mobile-first:** Tüm layout'u mobil için başlat, desktop'ta genişlet
- **Asimetrik grid dene:** Her şeyi ortalamak yerine sol-hizalı, güçlü tipografi

---

## 7. Çıktı Formatı

- Değişiklikler büyükse tek `index.html` içinde inline CSS + JS (CDN bağımlılığı olmadan çalışsın)
- Her çıktının sonunda kısa açıklama: Ne değişti, hangi renk paletini seçtin ve neden, hangi animasyon teknikleri eklendi — 3-5 madde

---

## 8. Kalite Kontrol

- [ ] Tasarım "AI klişesi" görünüyor mu? → Eğer evet, yeniden düşün
- [ ] Siteler birbirine benziyor mu? → Her site kendine özgü olmalı
- [ ] `prefers-reduced-motion` var mı?
- [ ] WCAG AA kontrast karşılanıyor mu? (özellikle açık temalarda)
- [ ] Mobilde düzgün görünüyor mu?
- [ ] Tüm Google Fonts linkleri `<head>` içinde mi?

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```
