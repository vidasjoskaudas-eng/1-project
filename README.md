# 1-project

Šitas projektas skirtas VPS ir SSH setup'ui bei paprastam web UI.

## Struktūra

- `web/` – paprastas frontend (HTML, CSS, JS).
- `scripts/` – viešieji skriptai (be slaptų duomenų).
- `docs/` – dokumentacija ir pastabos (be slaptų duomenų).
- `private/` – privatūs raktai ir prisijungimai (įtraukta į .gitignore).
  - `current-ssh/` – dabartiniai veikiantys SSH raktai.
  - `old-ssh-attempts/` – seni bandymai ir testiniai skriptai.

## Naudojimas

1. Atidaryk `1-project` folderį IDE.
2. Frontend redaguok `web/` viduje.
3. Dokumentaciją rasi `docs/` aplanke.
4. Slapti failai (raktai, .env ir pan.) visada turi būti tik `private/` aplanke.

## Saugumas

- `private/` aplankas yra ignoruojamas Git – jokia slapta informacija nepateks į repozitoriją.
- Prieš komitą visada patikrink `git status`.
- Niekada nerašyk tikrų raktų, slaptažodžių ar IP adresų į `web/`, `docs/` ar `scripts/`.
