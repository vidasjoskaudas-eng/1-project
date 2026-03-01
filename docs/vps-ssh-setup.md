# VPS SSH konfigūracija

Šis dokumentas aprašo, kaip sukonfigūruoti SSH prisijungimą prie VPS be slaptažodžio.

## Reikalavimai

- Windows 10/11 su OpenSSH klientu
- VPS serveris su SSH prieiga

## Žingsniai

### 1. Sugeneruoti SSH raktą (jei dar neturi)

```powershell
ssh-keygen -t ed25519 -C "tavo@email.com" -f "$env:USERPROFILE\.ssh\id_ed25519_vps"
```

Kai paklaus passphrase – gali palikti tuščią (Enter), jei nori jungtis be slaptažodžio.

### 2. Nukopijuoti viešą raktą į VPS

Prisijunk prie VPS su slaptažodžiu ir paleisk:

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh
echo 'TAVO_VIEŠAS_RAKTAS_ČIA' >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

### 3. Sukonfigūruoti SSH config failą

Sukurk/redaguok `%USERPROFILE%\.ssh\config`:

```
Host vps
    HostName TAVO_VPS_IP
    User root
    IdentityFile ~/.ssh/id_ed25519_vps
```

### 4. Prisijungti

```powershell
ssh vps
```

## Saugumo pastabos

- **NIEKADA** nekomituok privataus rakto (`id_ed25519_vps` be `.pub`) į Git
- Viešas raktas (`.pub`) yra saugus dalintis
- Geriausia praktika: naudoti passphrase su ssh-agent
