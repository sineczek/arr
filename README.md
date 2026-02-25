# 📦 ARR Stack — Media Automation Suite

ARR Stack to zestaw nowoczesnych aplikacji automatyzujących cały proces zarządzania multimediami — od wyszukiwania, przez pobieranie, po katalogowanie i aktualizację kolekcji.  
Aplikacje *Arr* takie jak Sonarr, Radarr, Lidarr, Readarr oraz narzędzia pomocnicze jak Prowlarr zapewniają kompletny przepływ pracy w ekosystemie samo‑hostowanych usług medialnych.  
[1](https://wiki.servarr.com/)

---

## 🚀 Jak działa ARR Stack?

Stack składa się z modułowych aplikacji, z których każda pełni określoną rolę.

### **Główne aplikacje Arr**

| Aplikacja | Opis |
|----------|------|
| **Sonarr** | Monitoruje i automatycznie pobiera seriale TV |
| **Radarr** | Automatyzuje pobieranie filmów |
| **Lidarr** | Organizuje i pobiera muzykę |
| **Readarr** | Zarządza e‑bookami |
| **Prowlarr** | Integruje indexery i przekazuje wyniki do pozostałych aplikacji |

Lista aplikacji *Arr*:  
[1](https://wiki.servarr.com/)

### **Przepływ działania**

1. Żądanie (np. film lub serial) trafia do Radarr lub Sonarr.  
2. Aplikacje korzystają z Prowlarr w celu wyszukania dostępnych treści.  
3. Dane są pobierane przez klienta download (np. qBittorrent).  
4. Po przetworzeniu pliki trafiają do docelowej biblioteki multimediów.  

Architektura przepływu została opisana w dokumentacji *Arr stack*:  
[2](https://www.filipbiljic.com/posts/homelab-arr-stack/)

---

# ▶️ TubeSync — Automatyczne archiwum YouTube

**TubeSync** to PVR dla YouTube, działający podobnie do Sonarr/Radarr, ale dla kanałów i playlist YouTube.  
Umożliwia:

- automatyczne pobieranie filmów z kanałów i playlist,  
- synchronizację nowych treści,  
- zapis lokalny audio/wideo,  
- integrację z Jellyfin lub Plex.  
[3](https://github.com/meeb/tubesync)

### Jak działa TubeSync?

- to webowy panel oparty o **yt-dlp** oraz **ffmpeg**,  
- posiada wbudowany harmonogram zadań,  
- używa mechanizmu back-off retry dla większej niezawodności.  
[3](https://github.com/meeb/tubesync)

Filmy i muzyka zapisywane są w katalogach `video/` oraz `audio/`:  
[4](https://django.wtf/repo/meeb/tubesync)

---

# 🎬 Jellyseerr — system zgłaszania próśb o multimedia

**Jellyseerr** to popularna aplikacja pozwalająca użytkownikom zgłaszać prośby o nowe filmy lub seriale, które następnie są automatycznie kierowane do Radarr i Sonarr.

> Brak wyników z wyszukiwarki — opis oparto na ogólnodostępnej publicznej dokumentacji Jellyseerr.

Funkcje:

- nowoczesny panel użytkownika,  
- integracja z Jellyfin/Plex,  
- automatyczne przekierowanie requestów do Radarr/Sonarr,  
- podgląd statusu pobierania.

---

# 📊 Jellystat — statystyki i analityka Jellyfin

**Jellystat** to zaawansowany dashboard analityczny dla Jellyfin.  
Pozwala przeglądać:

- statystyki oglądalności,  
- aktywność użytkowników,  
- popularne tytuły,  
- historię odtwarzań.

> Brak wyników z wyszukiwarki — opis oparto na znanych funkcjach projektu Jellystat.

---

# 🐳 Instalacja ARR stacka w Docker Compose

ARR Stack działa idealnie jako zestaw kontenerów Docker.  
Przykładowa konfiguracja Compose dla Sonarr / Radarr / Lidarr / Deluge / Prowlarr została opisana w jednym z przewodników:  
[5](https://www.jdbnet.co.uk/post/how-to-setup-an-arr-stack)
[6](https://www.youtube.com/watch?v=twJDyoj0tDc)
[7](https://github.com/TechHutTV/homelab/blob/main/media/README.md)
[8](https://github.com/qdm12/gluetun-wiki/blob/main/setup/providers/surfshark.md)

Po zdefiniowaniu usług wystarczy:

```bash
docker compose up -d