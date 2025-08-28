
# Renklerim (PWA) – Güneyler Elektrostatik

Mobil uyumlu, offline çalışan, kamera ile renk yakalayan RAL Classic renk paleti uygulaması.

## Özellikler
- Kategoriler (1000–9000) → seri listeleme
- Arama (kod/isim)
- Detay (HEX/RGB kopyalama), Favoriler (localStorage)
- Kamera: piksel rengi → en yakın RAL
- PWA (manifest + service worker), offline kullanım
- İkonlar (Ana ekrana ekle)

## Nasıl Yayınlanır? (GitHub Pages)
1. Bu repo dosyalarını GitHub'a yükleyin (örn. `renklerim-pwa`).
2. GitHub > Settings > Pages > Source: `Deploy from a branch` → Branch `main` → `/ (root)` → Save.
3. 1-2 dk içinde siteniz şu şekilde yayında olur: `https://<kullanici_adi>.github.io/renklerim-pwa/`

> Kamera ve PWA için **HTTPS** gerekir. GitHub Pages otomatik HTTPS sağlar.

## Yerel Geliştirme
```bash
# Python ile basit server
python -m http.server 8000
# sonra tarayıcıda
http://localhost:8000
```
Not: `ral_colors.json` dosyasını topluluk verisiyle hazır verdik. Kendi veri setinizi aynı şemada değiştirip kullanabilirsiniz:
```json
[{"code":"RAL 3020","name":"Traffic red","hex":"#CC0000"}]
```

## Dosya Yapısı
- `index.html` – Uygulama (kategori, detay, favori, kamera)
- `ral_colors.json` – RAL verisi
- `sw.js` – Service worker (offline cache)
- `manifest.webmanifest` – PWA manifest
- `assets/icons/` – Uygulama ikonları
- `.nojekyll` – GitHub Pages Jekyll işlemeyi kapatır
```