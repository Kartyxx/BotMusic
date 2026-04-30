# BotMusic 🎶

Bot Discord de musique basé sur **discord.js v14**. Lecture YouTube, Spotify, SoundCloud et liens directs, avec une interface entièrement en embeds.

---

## Fonctionnalités

- Commandes slash : `/play`, `/search`, `/nowplaying`, `/language`, `/help`
- Lecture depuis YouTube, Spotify, SoundCloud, liens MP3/WAV/OGG directs
- File d'attente avec shuffle, loop (titre / file entière), autoplay par genre
- Cache audio local (téléchargement avant lecture = zéro coupure)
- 21 langues disponibles, changement en temps réel par serveur
- Sharding intégré pour les bots sur 1000+ serveurs

---

## Installation

### Prérequis

- Node.js ≥ 24
- Un bot Discord créé sur le [portail développeur](https://discord.com/developers/applications)

### Lancer le bot

```bash
npm install
node index.js
```

---

## Configuration

Crée un fichier `.env` à la racine (un `.env` d'exemple est présent dans le repo) :

```env
# Obligatoire
DISCORD_TOKEN=ton_token_discord
CLIENT_ID=ton_client_id

# Optionnel — pour les commandes en test rapide sur un seul serveur
GUILD_ID=ton_server_id

# Optionnel — pour les liens Spotify
SPOTIFY_CLIENT_ID=
SPOTIFY_CLIENT_SECRET=

# Optionnel — pour les paroles via l'API Genius (fonctionne sans via scraping)
GENIUS_CLIENT_ID=
GENIUS_CLIENT_SECRET=

# Apparence
STATUS=🎵 Mon Bot | /play
EMBED_COLOR=#FF6B6B
```

---

## Commandes

| Commande | Description |
|---|---|
| `/play <recherche ou lien>` | Lance une musique ou une playlist |
| `/search <mots-clés>` | Affiche une liste de résultats YouTube à choisir |
| `/nowplaying` | Réaffiche l'embed en cours |
| `/language` | Change la langue du bot sur ce serveur |
| `/help` | Affiche l'aide |

### Boutons dans l'embed

| Bouton | Action |
|---|---|
| ⏸️ / ▶️ | Pause / Reprendre |
| ⏭️ | Passer au suivant |
| ⏹️ | Arrêter et vider la file |
| 📋 | Afficher la file d'attente |
| 🔀 | Mélanger la file |
| 🔊 | Changer le volume (0–100) |
| 🔁 | Changer le mode de répétition |
| 🎲 | Activer l'autoplay par genre |

---

## Problèmes courants

| Symptôme | Solution |
|---|---|
| Les commandes slash n'apparaissent pas | Vérifie que `CLIENT_ID` est correct. Pour un déploiement rapide, utilise `GUILD_ID`. |
| Spotify ne retourne rien | Vérifie `SPOTIFY_CLIENT_ID` et `SPOTIFY_CLIENT_SECRET`. |
| Erreur de détection de bot YouTube | YouTube bloque yt-dlp. Ajoute `COOKIES_FROM_BROWSER=chrome` (ou `firefox`) dans `.env`. |
| Le bot rejoint mais ne joue rien | Vérifie les permissions **Connexion** et **Parler** sur le salon vocal. |

---

## Structure

```
MusicBot/
├── commands/       # Commandes slash
├── events/         # Gestionnaires de boutons et modals
├── src/            # Logique principale (lecteur, providers, embeds...)
├── languages/      # 21 fichiers de traduction JSON
├── database/       # Préférences de langue par serveur
├── config.js       # Configuration centrale
└── index.js        # Point d'entrée
```

---

## Licence

MIT — voir [LICENSE](./LICENSE).
