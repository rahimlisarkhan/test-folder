# 📘 Tələbə üçün bələdçi — MySite

Bu layihə **HTML və CSS** öyrənən tələbələr üçün sadə bir veb saytdır.
Saytda 2 səhifə var: **Home** (ana səhifə) və **About** (haqqımızda).

---

## 📁 Layihənin strukturu

```
test-folder/
├── index.html          → Ana səhifə (Home)
├── pages/
│   └── about.html      → Haqqımızda səhifəsi (About)
├── styles/
│   ├── reset.css       → Brauzerin default stillərini sıfırlayır
│   └── global.css      → Saytın əsas stilləri
├── README.md
└── STUDENT.md          → Bu fayl
```

---

## ▶️ Layihəni necə açmaq olar?

1. `index.html` faylını brauzerdə açın (faylın üzərinə iki dəfə klikləyin).
2. Və ya VS Code-da **Live Server** extension-u ilə açın:
   `index.html` → sağ klik → **Open with Live Server**.

---

## 🧱 HTML — nə öyrəndik?

Səhifələrdə **semantic** (mənalı) teqlərdən istifadə olunub:

| Teq         | Nə üçündür?                         |
| ----------- | ----------------------------------- |
| `<header>`  | Saytın yuxarı hissəsi (logo, menyu) |
| `<nav>`     | Naviqasiya linkləri                 |
| `<main>`    | Səhifənin əsas məzmunu              |
| `<section>` | Məzmunun ayrıca bölməsi (kart)      |
| `<footer>`  | Saytın aşağı hissəsi                |

### Linklər və yollar (paths)

- `index.html`-dən about səhifəsinə: `./pages/about.html`
- `about.html`-dən ana səhifəyə: `../index.html`
- `./` — eyni qovluq, `../` — bir qovluq yuxarı

---

## 🎨 CSS — nə öyrəndik?

### 1. `reset.css`

Hər brauzerin öz default stilləri var (margin, padding və s.).
`reset.css` bunları sıfırlayır ki, sayt bütün brauzerlərdə eyni görünsün.

```css
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

> ⚠️ `reset.css` həmişə `global.css`-dən **əvvəl** qoşulmalıdır.

### 2. `.container`

Məzmunu ortalayır və maksimum eni məhdudlaşdırır:

```css
.container {
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 16px;
}
```

### 3. Flexbox

Header-də logo solda, menyu sağda dursun deyə:

```css
.header .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### 4. Responsive dizayn (`@media`)

| Ekran        | Şərt                | `.container` eni |
| ------------ | ------------------- | ---------------- |
| Desktop      | 1440px-dən böyük    | 1440px           |
| Desktop orta | `max-width: 1440px` | 1200px           |
| Tablet       | `max-width: 1023px` | 720px            |
| Mobil        | `max-width: 600px`  | 100%             |

### 5. Footer-i aşağıda saxlamaq

`body` flex sütun olur, `main` isə boş yeri doldurur:

```css
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.main {
  flex: 1;
}
```

---

## ✍️ Tapşırıqlar

1. **Contact** səhifəsi yaradın: `pages/contact.html`.
   Header və footer-i digər səhifələrdən kopyalayın.
2. Bütün səhifələrin menyusuna **Contact** linkini əlavə edin.
3. Home səhifəsinə daha 2 ədəd `.card` əlavə edin.
4. Kartları yan-yana düzmək üçün Flexbox və ya Grid istifadə edin.
5. Mobil ekranda (`max-width: 600px`) menyu linklərini alt-alta düzün.
6. `.card` üçün `:hover` effekti əlavə edin (məs. kölgə — `box-shadow`).

---

## 💾 Git əmrləri (xatırlatma)

```bash
git status                 # dəyişiklikləri görmək
git add .                  # bütün faylları əlavə etmək
git commit -m "mesaj"      # commit etmək
git log --oneline          # tarixçəyə baxmaq
```

---

Uğurlar! 🚀
