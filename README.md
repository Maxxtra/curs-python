# Curs Python – laboratoare în browser (JupyterLite)

Python rulează direct în browser, fără instalare și fără cont. Notebook-urile din `content/` devin
pagini pe GitHub Pages.

## Linkuri

| Lecția | Elevi | Profesor (cu soluții) |
|---|---|---|
| IX A – Lecția 1: Primii pași în Python | https://maxxtra.github.io/curs-python/ix/a/lectia1/ | https://maxxtra.github.io/curs-python/sol/ix/a/lectia1/ |
| IX A – Lecția 2: Bucle și funcții | https://maxxtra.github.io/curs-python/ix/a/lectia2/ | https://maxxtra.github.io/curs-python/sol/ix/a/lectia2/ |
| IX A – Lecția 3: Prima aplicație | https://maxxtra.github.io/curs-python/ix/a/lectia3/ | https://maxxtra.github.io/curs-python/sol/ix/a/lectia3/ |
| IX B – Lecția 1: Primii pași în Python | https://maxxtra.github.io/curs-python/ix/b/lectia1/ | https://maxxtra.github.io/curs-python/sol/ix/b/lectia1/ |
| IX B – Lecția 2: Bucle și funcții | https://maxxtra.github.io/curs-python/ix/b/lectia2/ | https://maxxtra.github.io/curs-python/sol/ix/b/lectia2/ |
| IX B – Lecția 2: Misiunea Python | https://maxxtra.github.io/curs-python/ix/b/lectia2/misiune/ | https://maxxtra.github.io/curs-python/sol/ix/b/lectia2/misiune/ |
| X A – Lecția 1: Liste, texte, dicționare | https://maxxtra.github.io/curs-python/x/a/lectia1/ | https://maxxtra.github.io/curs-python/sol/x/a/lectia1/ |
| X A – Lecția 2: Prima aplicație în echipă | https://maxxtra.github.io/curs-python/x/a/lectia2/ | https://maxxtra.github.io/curs-python/sol/x/a/lectia2/ |

Format: `curs-python/<clasa>/<litera>/lectiaN/`, de ex. `curs-python/ix/a/lectia2/`. Linkurile vechi (`lab1/`, `lab2b/`, `xa1/` …) merg în continuare.

Varianta de profesor e un site JupyterLite separat (`profesor/`), construit în `dist/sol/`, deci nu apare
în browserul de fișiere al elevilor. Linkul nu e dat nicăieri public, dar fișierele sunt vizibile în repo-ul public.

## Publicare (o singură dată, ~5 minute)

1. Pe GitHub: **New repository** → numele `curs-python`, public, fără README. 
2. Local:
   ```bash
   cd curs-python
   git init -b main
   git add .
   git commit -m "Lab 1: primii pași în Python"
   git remote add origin https://github.com/maxxtra/curs-python.git
   git push -u origin main
   ```
3. Pe GitHub, în repo: **Settings → Pages → Source: GitHub Actions**.
4. Tab-ul **Actions**: primul build durează 1–2 minute. Când e verde, linkurile de mai sus merg.

Orice `git push` ulterior republică automat.

## Adăugarea unui laborator nou

1. Notebook-ul elevilor în `content/<folder>/`, cel de profesor în `profesor/content/<folder>/`.
2. Linkurile scurte: `redirects/<clasa>/<litera>/lectiaN/index.html` și `redirects/sol/<clasa>/<litera>/lectiaN/index.html` (copie după unul existent, cu titlul și calea notebook-ului schimbate).
3. `git push`.

## Bun de știut

- Ce scriu elevii se salvează **în browserul lor** (IndexedDB), nu pe server. Fiecare elev vede
  notebook-ul original la prima deschidere și propriile modificări la următoarele, pe același
  calculator și browser. Pentru a lua lucrul acasă: **File → Download**.
- Dacă schimbi notebook-ul din `content/` după ce un elev l-a deschis deja, el vede în continuare
  versiunea lui salvată local. Cel mai simplu: pune versiunea nouă sub alt nume de fișier.
- `input()` funcționează (apare o căsuță sub celulă), la fel `random`, `math` și bibliotecile
  standard. Pandas și matplotlib se pot instala din notebook cu `%pip install pandas matplotlib`
  (pentru zilele următoare).
- Prima încărcare descarcă ~20 MB (Python pentru browser); după aceea e rapid.

## Test local

```bash
pip install -r requirements.txt
jupyter lite build
jupyter lite serve      # http://localhost:8000
```
