# MagisterkaOnline.com.pl

Kompleksowy poradnik pisania prac magisterskich - od pomysłu do obrony.

## 🚀 Technologie

- **Astro** - statyczny generator stron
- **Tailwind CSS** - stylowanie
- **TypeScript** - type safety

## 📁 Struktura Projektu

```
/
├── public/             # Statyczne assety (obrazy, ikony)
├── src/
│   ├── components/     # Komponenty wielokrotnego użytku
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── Card.astro
│   │   ├── Section.astro
│   │   └── FeatureGrid.astro
│   ├── layouts/        #Layouty stron
│   │   └── Layout.astro
│   ├── pages/          # Strony (routing)
│   │   ├── index.astro
│   │   ├── poradnik-pisania/
│   │   │   ├── index.astro
│   │   │   ├── jak-zaczac.astro
│   │   │   └── ...
│   │   └── ai-w-pisaniu-prac-mgr/
│   └── styles/         # Globalne style
│       └── global.css
└── package.json
```

## 🛠️ Komendy

| Komenda           | Akcja                                     |
| :---------------- | :---------------------------------------- |
| `npm install`     | Instalacja zależności                     |
| `npm run dev`     | Uruchomienie dev servera `localhost:4321` |
| `npm run build`   | Build produkcyjny do `./dist/`            |
| `npm run preview` | Podgląd buildu przed deploymentem         |

## 🎨 Design System

### Kolory

- **Primary**: Niebieski (`primary-50` do `primary-900`)
- **Accent**: Fioletowy (`accent-50` do `accent-900`)

### Komponenty

- `Header` - Nawigacja sticky z mobile menu
- `Footer` - Stopka z linkami i social media
- `Hero` - Sekcja hero z CTA
- `Card` - Karta z wariantami (default, bordered, elevated)
- `Section` - Wrapper dla sekcji z opcjonalnym tytułem
- `FeatureGrid` - Grid dla feature'ów

### Utility Classes

- `.container-custom` - Kontener z max-width
- `.btn-primary` - Główny przycisk
- `.btn-secondary` - Drugorzędny przycisk
- `.card` - Podstawowa karta
- `.section-padding` - Padding dla sekcji

## 📝 Dodawanie Nowego Poradnika

1. Utwórz nowy plik w `src/pages/poradnik-pisania/nazwa-poradnika.astro`
2. Użyj layoutu: `import Layout from '../../layouts/Layout.astro'`
3. Dodaj metadata SEO (title, description)
4. Użyj komponentów `Section`, `Card` dla spójnego designu

## 🚀 Deployment (AWS)

### Przygotowanie

1. Build projektu: `npm run build`
2. Folder `dist/` zawiera statyczne pliki

### AWS Setup

1. **S3 Bucket**

   - Utwórz bucket z nazwą domeny: `magisterkaonline.com.pl`
   - Włącz static website hosting
   - Upload plików z `dist/`

2. **CloudFront**

   - Utwórz dystrybucję CloudFront
   - Origin: Twój S3 bucket
   - Domyślny root object: `index.html`
   - Custom error responses: 404 → /404.html

3. **Route 53**
   - Dodaj rekord A (Alias) wskazujący na CloudFront

## 📄 License

© 2025 MagisterkaOnline.pl - Wszelkie prawa zastrzeżone
