# albezam.github.io

GitHub Pages organization site для **AL BEZAM GROUP**.

- **Production URL:** https://albezam.ae (после распространения DNS)
- **Default GitHub URL:** https://albezam.github.io
- **Source branch:** `gh-pages`

## Что здесь

Минималистичная заглушка-landing на чистом HTML + CSS + 30 строк JS для переключения языка (EN/RU).
Без фреймворков, без build-process. GitHub Pages обслуживает статику.

| Файл | Назначение |
|---|---|
| `index.html` | Single-page landing с переключением EN/RU |
| `CNAME` | Custom domain `albezam.ae` |
| `.nojekyll` | Отключение Jekyll processing (GitHub Pages подаёт файлы как есть) |
| `robots.txt` | Разрешает индексацию всем поисковикам |
| `sitemap.xml` | Sitemap для SEO |

## Brand

Цвета, шрифты, токены — синхронизированы с [`albezam/brand`](https://github.com/albezam/brand) репо:
- Background: `#060810` (navy)
- Accent: `#00BFA5` (cyan)
- Card / surface: `#1F2E45` (navy-light)
- Body text: Inter (Google Fonts)
- Display text: Space Grotesk (Google Fonts)

При обновлении бренда в `albezam/brand/tokens/colors.json` — синхронизируется руками в `index.html` (одна страница, нет смысла строить pipeline).

## Локальная разработка

```bash
cd ~/work/albezam/albezam.github.io
python3 -m http.server 8000
# открыть http://localhost:8000
```

Или просто открыть `index.html` двойным кликом в браузере.

## Деплой

Push в ветку `gh-pages` → GitHub Pages автоматически публикует.

```bash
git checkout gh-pages
git add -A && git commit -m "..."
git push origin gh-pages
```

Первый раз: Settings → Pages → Source = `gh-pages` branch, `/ (root)`.

## DNS настройка (один раз)

В nic.ae для домена `albezam.ae`:
```
ALIAS @     →  albezam.github.io.
CNAME www   →  albezam.github.io.
```
Или 4 A-записи `@` на IP-адреса GitHub Pages:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

GitHub auto-issue SSL Let's Encrypt сертификат после распространения DNS.
В Settings → Pages → Custom domain = `albezam.ae` → Enforce HTTPS (после получения сертификата).

## Когда это уйдёт в архив

Эта заглушка живёт пока:
1. Не будет полноценного сайта в [`albezam/website`](https://github.com/albezam/website) репо (Next.js / Vue / etc.)
2. Или пока команда не решит развить эту заглушку до полноценного landing

После этого — либо переключить Pages на репо `website/`, либо обновить здесь до полноценного сайта.
