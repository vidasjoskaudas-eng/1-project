# Projekto struktūra

## Aplankų aprašymas

```
1-project/
├── web/              # Frontend failai (HTML, CSS, JS)
├── scripts/          # Viešieji skriptai (be slaptų duomenų)
├── docs/             # Dokumentacija
├── private/          # Slapti failai (ignoruojama Git)
│   ├── current-ssh/  # Dabartiniai veikiantys SSH raktai
│   └── old-ssh-attempts/  # Seni bandymai ir testiniai skriptai
└── .gitignore        # Git ignoruojami failai
```

## Saugumo taisyklės

1. **private/** aplankas NIEKADA neturi patekti į Git
2. SSH privatūs raktai turi būti tik `private/current-ssh/`
3. Jokių tikrų IP adresų, slaptažodžių ar raktų `docs/` ar `web/` aplankuose
4. Prieš komitą visada patikrink `git status`

## Darbo eiga

1. Frontend kūrimas → `web/`
2. Dokumentacija → `docs/`
3. Slapti konfiguracijos failai → `private/`
