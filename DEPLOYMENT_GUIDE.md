# 🚀 GGRD Website - Instrukcje Deployment

## 📋 Spis Treści

1. [Wymagania](#wymagania)
2. [Pierwszy Deploy na GitHub](#pierwszy-deploy-na-github)
3. [Aktualizacja Strony](#aktualizacja-strony)
4. [Konfiguracja GitHub Pages](#konfiguracja-github-pages)
5. [Konfiguracja Custom Domain](#konfiguracja-custom-domain)

---

## ✅ Wymagania

### Wymagane:
- **Git** - [Pobierz tutaj](https://git-scm.com/download/win)
- **Konto GitHub** - [Załóż tutaj](https://github.com/signup)

### Opcjonalne (polecane):
- **GitHub CLI** - [Pobierz tutaj](https://cli.github.com/)

---

## 🎯 PIERWSZY DEPLOY NA GITHUB

### Krok 1: Przygotowanie

1. **Otwórz PowerShell** jako Administrator
2. **Pozwól na wykonywanie skryptów** (jednorazowo):
   ```powershell
   Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
   ```

### Krok 2: Konfiguracja

1. **Otwórz plik** `deploy-to-github.ps1` w edytorze
2. **Zmień** te wartości na początku pliku:

```powershell
$GITHUB_USERNAME = "TWOJ_GITHUB_USERNAME"  # ← ZMIEŃ NA SWOJĄ NAZWĘ!
$REPO_NAME = "GGRD_Website"                # Możesz zmienić nazwę repo
$REPO_VISIBILITY = "public"                # "public" lub "private"
```

**Przykład:**
```powershell
$GITHUB_USERNAME = "piotr_crypto"
$REPO_NAME = "GGRD_Website"
$REPO_VISIBILITY = "public"
```

### Krok 3: Uruchomienie Skryptu

#### **Opcja A: Z GitHub CLI (Automatyczna - POLECANA)**

1. **Zaloguj się** do GitHub CLI (jednorazowo):
   ```powershell
   gh auth login
   ```
   - Wybierz: **GitHub.com**
   - Wybierz: **HTTPS**
   - Wpisz: **Y** (zaloguj przez przeglądarkę)

2. **Uruchom skrypt:**
   ```powershell
   cd C:\APLIKACJE\GGRD_Website
   .\deploy-to-github.ps1
   ```

3. **Gotowe!** 🎉 Repozytorium utworzone i kod wypushowany!

#### **Opcja B: Bez GitHub CLI (Manualna)**

1. **Uruchom skrypt:**
   ```powershell
   cd C:\APLIKACJE\GGRD_Website
   .\deploy-to-github.ps1
   ```

2. **Stwórz repo ręcznie:**
   - Otwórz: https://github.com/new
   - **Repository name:** `GGRD_Website`
   - **Visibility:** Public
   - **NIE** zaznaczaj "Initialize with README"
   - Kliknij **Create repository**

3. **Wpisz "T"** gdy skrypt zapyta o push

4. **Gotowe!** 🎉

---

## 🔄 AKTUALIZACJA STRONY (Po zmianach)

Po każdej zmianie w plikach (np. aktualizacja `index.html`):

### Metoda 1: Użyj Skryptu `quick-update.ps1`

```powershell
cd C:\APLIKACJE\GGRD_Website
.\quick-update.ps1
```

Lub z custom wiadomością:
```powershell
.\quick-update.ps1 -Message "Updated tokenomics section"
```

### Metoda 2: Manualne Komendy Git

```powershell
cd C:\APLIKACJE\GGRD_Website

# Dodaj zmiany
git add .

# Commit
git commit -m "Update website"

# Push
git push origin main
```

---

## 🌐 KONFIGURACJA GITHUB PAGES

### Krok 1: Włącz GitHub Pages

1. Przejdź do repozytorium na GitHub
2. **Settings** → **Pages** (w lewym menu)
3. **Source:**
   - Branch: `main`
   - Folder: `/ (root)`
4. **Save**

### Krok 2: Sprawdź

Po ~1-2 minutach strona będzie dostępna na:
```
https://TWOJ_USERNAME.github.io/GGRD_Website/
```

---

## 🏷️ KONFIGURACJA CUSTOM DOMAIN (ggrd.me)

### Krok 1: GitHub Settings

1. **Settings** → **Pages**
2. **Custom domain:** `ggrd.me`
3. **Save**
4. Zaznacz: ✅ **Enforce HTTPS** (poczekaj 5-10 min)

### Krok 2: Hostinger DNS Settings

1. Zaloguj się na **Hostinger**: https://hpanel.hostinger.com
2. **Domains** → `ggrd.me` → **DNS / Name Servers**
3. **Usuń** stare rekordy A/CNAME dla `@` i `www`
4. **Dodaj nowe rekordy:**

| Type | Name | Value | TTL |
|------|------|-------|-----|
| **A** | @ | `185.199.108.153` | 14400 |
| **A** | @ | `185.199.109.153` | 14400 |
| **A** | @ | `185.199.110.153` | 14400 |
| **A** | @ | `185.199.111.153` | 14400 |
| **CNAME** | www | `TWOJ_USERNAME.github.io` | 14400 |

5. **Save Changes**

### Krok 3: Poczekaj na Propagację DNS

- **Czas:** 10-60 minut
- **Sprawdź:** https://ggrd.me

---

## 🔧 TROUBLESHOOTING

### Problem: "git: command not found"
**Rozwiązanie:** Zainstaluj Git z https://git-scm.com/download/win

### Problem: "cannot be loaded because running scripts is disabled"
**Rozwiązanie:**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Problem: "remote: Repository not found"
**Rozwiązanie:** 
- Sprawdź czy nazwa użytkownika jest poprawna w skrypcie
- Sprawdź czy repozytorium zostało utworzone na GitHub
- Sprawdź uprawnienia (jeśli private repo)

### Problem: GitHub Pages pokazuje 404
**Rozwiązanie:**
- Poczekaj 2-5 minut po pierwszym push
- Sprawdź czy w Settings → Pages jest włączone
- Sprawdź czy branch to `main` (nie `master`)

### Problem: DNS nie działa po 1h
**Rozwiązanie:**
- Sprawdź czy rekordy DNS są poprawnie ustawione
- Użyj https://dnschecker.org/ do sprawdzenia propagacji
- Czasem propagacja może trwać do 24h (rzadko)

---

## 📚 Przydatne Komendy Git

```powershell
# Sprawdź status
git status

# Zobacz historię commitów
git log --oneline

# Zobacz zmiany w plikach
git diff

# Cofnij zmiany (przed commit)
git restore nazwa_pliku.html

# Zobacz remote URL
git remote -v

# Zmień remote URL
git remote set-url origin https://github.com/USERNAME/REPO.git
```

---

## 🎯 Workflow - Przykład Pracy

```powershell
# 1. Edytujesz index.html w edytorze
# 2. Zapisujesz zmiany
# 3. Uruchamiasz quick update:

cd C:\APLIKACJE\GGRD_Website
.\quick-update.ps1 -Message "Added new tokenomics chart"

# 4. Poczekaj ~1-2 minuty
# 5. Sprawdź https://ggrd.me
```

---

## ✅ Checklist Pierwszego Deployu

- [ ] Git zainstalowany
- [ ] Konto GitHub utworzone
- [ ] Zmieniono `$GITHUB_USERNAME` w skrypcie
- [ ] Uruchomiono `deploy-to-github.ps1`
- [ ] Repozytorium utworzone na GitHub
- [ ] Kod wypushowany
- [ ] GitHub Pages włączone
- [ ] Custom domain ustawione (opcjonalnie)
- [ ] DNS skonfigurowane (opcjonalnie)
- [ ] HTTPS działa ✅

---

## 📞 Wsparcie

- **GitHub Issues:** https://github.com/TWOJ_USERNAME/GGRD_Website/issues
- **Telegram:** https://t.me/GGRDchat

---

**Powered by GGRD Team 💚**
