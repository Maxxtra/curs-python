# Curs Python – laboratoare în browser (JupyterLite)

Python rulează direct în browser, fără instalare și fără cont. Notebook-urile din `content/` devin
pagini pe GitHub Pages.

## Linkuri (după publicare)

| Ce | Link |
|---|---|
| Ziua 1, notebook pentru elevi (vedere simplă, recomandat) | `https://alexdeonise.github.io/curs-python/notebooks/index.html?path=lab1/Ziua1_Python_ELEVI.ipynb` |
| Ziua 1, în JupyterLab complet | `https://alexdeonise.github.io/curs-python/lab/index.html?path=lab1/Ziua1_Python_ELEVI.ipynb` |
| Pagina principală (toate fișierele) | `https://alexdeonise.github.io/curs-python/` |

## Publicare (o singură dată, ~5 minute)

1. Pe GitHub: **New repository** → numele `curs-python`, public, fără README. 
2. Local:
   ```bash
   cd curs-python
   git init -b main
   git add .
   git commit -m "Lab 1: primii pași în Python"
   git remote add origin https://github.com/alexdeonise/curs-python.git
   git push -u origin main
   ```
3. Pe GitHub, în repo: **Settings → Pages → Source: GitHub Actions**.
4. Tab-ul **Actions**: primul build durează 1–2 minute. Când e verde, linkurile de mai sus merg.

Orice `git push` ulterior republică automat.

## Adăugarea unui laborator nou

Pui notebook-ul în `content/lab2/` (sau orice folder), `git push`, gata. Linkul devine
`.../notebooks/index.html?path=lab2/<nume>.ipynb`.

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
