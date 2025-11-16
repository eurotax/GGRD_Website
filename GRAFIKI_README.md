# 📸 Wymagane Grafiki dla GGRD Website

## 🎯 Lista Plików

### 1. logo.png (WYMAGANE)
**Lokalizacja:** `img/logo.png`
**Zalecane wymiary:** 512x512 pikseli
**Format:** PNG z przezroczystym tłem
**Wykorzystanie:** 
- Logo w header'ze (48x48px po zmniejszeniu)
- Favicon (możesz wygenerować z tego pliku)

**Możliwe źródła:**
- `C:\APLIKACJE\Strona TOKEN NOWY\logo_gold.png` (jeśli istnieje)
- Wygeneruj nowe logo z motywem Robin Hood + lis
- Zamów u grafika (Fiverr, Upwork)

**Fallback:** Jeśli brak - zostanie pokazany tylko tekst "GGRD"

---

### 2. robin.png (WYMAGANE)
**Lokalizacja:** `img/robin.png`
**Zalecane wymiary:** 800x800 pikseli lub więcej
**Format:** PNG z przezroczystym tłem
**Wykorzystanie:**
- Główna maskotka w sekcji Hero (400px na desktop, 280px na mobile)
- Powinien być "Robin of Gains" - lis w stroju Robin Hooda

**Koncepcja postaci:**
- 🦊 Lis (base character)
- 🏹 Z łukiem i strzałami Robin Hooda
- 🎩 W zielonym kapelusiku z piórkiem
- 💰 Może trzymać worek ze złotem/tokenami
- 😄 Uśmiechnięty, przyjazny, memowy vibe

**Możliwe źródła:**
- Zamów u grafika (podaj brief: "Fox as Robin Hood, meme style, friendly, holding bow")
- Wygeneruj AI (Midjourney, DALL-E): "cartoon fox dressed as Robin Hood, holding bow, meme style, vibrant colors, transparent background"
- Użyj stock graphics i customizuj (np. Canva)

**Fallback:** Jeśli brak - zostanie pokazana duża emoji: 🦊

---

### 3. og-image.png (OPCJONALNE ale zalecane)
**Lokalizacja:** `img/og-image.png`
**Wymagane wymiary:** 1200x630 pikseli (format Open Graph)
**Format:** PNG lub JPG
**Wykorzystanie:**
- Podgląd gdy ktoś udostępni link na Twitter, Facebook, Telegram
- Pokazuje się w Discord embeds

**Co powinno zawierać:**
- Logo GGRD lub maskotka Robin of Gains
- Tekst: "GGRD - Robin of Gains"
- Tagline: "Steal from curves, give to the people"
- Można dodać: "No Presale • Zero Tax • Fair Launch"
- Background: ciemny z neonowymi akcentami (lime + gold)

**Możliwe źródła:**
- Canva template "Facebook Cover" (1200x630)
- Photoshop/Figma
- Online tool: https://www.opengraph.xyz/

**Fallback:** Jeśli brak - linki będą działać, ale bez podglądu obrazu

---

### 4. favicon.ico (OPCJONALNE)
**Lokalizacja:** katalog główny lub `img/favicon.ico`
**Wymiary:** 16x16, 32x32, 48x48 pikseli (multi-size ICO file)
**Format:** .ico
**Wykorzystanie:**
- Ikonka w zakładce przeglądarki
- Bookmarks

**Jak stworzyć:**
1. Użyj `logo.png` jako podstawy
2. Konwertuj na .ico używając: https://favicon.io/
3. Upload plik i dodaj do `<head>`:
   ```html
   <link rel="icon" type="image/x-icon" href="./favicon.ico">
   ```

---

## 🛠️ Jak Dodać Grafiki

### Opcja A: Manualne kopiowanie
```cmd
# Z katalogu C:\APLIKACJE\Strona TOKEN NOWY (jeśli istnieją)
copy "C:\APLIKACJE\Strona TOKEN NOWY\logo_gold.png" "C:\APLIKACJE\GGRD_Website\img\logo.png"
copy "C:\APLIKACJE\Strona TOKEN NOWY\og-image_gold.png" "C:\APLIKACJE\GGRD_Website\img\og-image.png"
```

### Opcja B: PowerShell
```powershell
Copy-Item "C:\APLIKACJE\Strona TOKEN NOWY\*.png" -Destination "C:\APLIKACJE\GGRD_Website\img\"
```

### Opcja C: Explorer
1. Otwórz `C:\APLIKACJE\Strona TOKEN NOWY\`
2. Zaznacz wszystkie PNG
3. Kopiuj (Ctrl+C)
4. Wklej do `C:\APLIKACJE\GGRD_Website\img\` (Ctrl+V)
5. Zmień nazwy na: `logo.png`, `robin.png`, `og-image.png`

---

## ✅ Checklist

- [ ] `img/logo.png` dodany (512x512px, PNG)
- [ ] `img/robin.png` dodany (800x800px, PNG)
- [ ] `img/og-image.png` dodany (1200x630px, PNG/JPG)
- [ ] `favicon.ico` dodany (opcjonalnie)
- [ ] Wszystkie pliki mają przezroczyste tła (gdzie stosowne)
- [ ] Grafiki są zoptymalizowane (nie większe niż 500KB każda)
- [ ] Test w przeglądarce pokazuje obrazy poprawnie

---

## 🎨 Narzędzia do Tworzenia Grafik

**Free:**
- Canva: https://canva.com (templates, easy to use)
- GIMP: https://gimp.org (Photoshop alternative)
- Inkscape: https://inkscape.org (vector graphics)
- Figma: https://figma.com (UI/UX design)

**AI Generation:**
- Midjourney: https://midjourney.com (best quality, $10/mo)
- DALL-E: https://openai.com/dall-e (via ChatGPT Plus)
- Stable Diffusion: https://stablediffusionweb.com (free)

**Optimization:**
- TinyPNG: https://tinypng.com (compress images)
- Squoosh: https://squoosh.app (Google's image compressor)

---

## 📏 Wymiary Referencyjne

```
Logo (Header):        48x48px   (display size)
Logo (Source):       512x512px  (high-res source)
Maskotka (Hero):     400x400px  (display size desktop)
Maskotka (Mobile):   280x280px  (display size mobile)
Maskotka (Source):   800x800px+ (high-res source)
OG Image:           1200x630px  (exact dimensions)
Favicon:             32x32px    (most common size)
```

---

**STATUS:** ⚠️ Oczekuję na dodanie grafik

Po dodaniu grafik uruchom `index.html` w przeglądarce i sprawdź czy wszystko wyświetla się poprawnie!
