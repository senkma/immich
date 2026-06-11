# Immich - Self-hosted Photo Backup

Automatická synchronizace fotek z iOS na vlastní server.

## 🚀 Jak spustit

### 1. Nastavení

Edituj `.env` soubor a **změň heslo k databázi**:
```bash
DB_PASSWORD=CHANGE_ME_TO_RANDOM_PASSWORD
```

### 2. Spuštění

```bash
docker compose up -d
```

### 3. První přístup

Otevři v prohlížeči:
```
http://localhost:2283
```

Při prvním přístupu vytvoř admin účet.

## 📱 iOS Aplikace

1. Stáhni **Immich** z App Store
2. V aplikaci zadej URL tvého serveru (např. `https://photos.tvojadomena.cz`)
3. Přihlas se účtem, který jsi vytvořil
4. Zapni automatické zálohovánív nastavení

## 🔧 Coolify Deployment

V Coolify:
1. Vytvoř nový projekt typu "Docker Compose"
2. Připoj tento Git repozitář
3. Nastav environment proměnné (hlavně `DB_PASSWORD`)
4. Nastav domain (např. `photos.tvojadomena.cz`)
5. Deploy!

## 📁 Důležité složky

- `./library` - zde se ukládají všechny fotky a videa
- `./postgres` - databáze (nezálohuj na síťové disky!)

## 🔒 Bezpečnost

- **Změň `DB_PASSWORD`** v `.env` souboru!
- Použij HTTPS (Coolify to zařídí automaticky)
- Nastav silné heslo pro admin účet

## 📚 Dokumentace

- [Immich Documentation](https://docs.immich.app/)
- [iOS App Store](https://apps.apple.com/app/immich/id1613945652)

## ⚙️ Pokročilé nastavení

### Hardware acceleration (transcoding)
Pro rychlejší zpracování videí můžeš povolit HW akceleraci - viz [dokumentace](https://docs.immich.app/features/hardware-transcoding).

### Backup
Pravidelně zálohuj složky:
- `./library` - tvoje fotky a videa
- `./postgres` - databáze

## 🆘 Troubleshooting

### Restart služeb
```bash
docker compose restart
```

### Zobrazit logy
```bash
docker compose logs -f immich-server
```

### Zastavit vše
```bash
docker compose down
```

### Zastavit a smazat vše (včetně dat!)
```bash
docker compose down -v
```
