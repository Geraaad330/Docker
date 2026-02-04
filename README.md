# 🐳 HomeLab Docker Collection

Repozytorium zawiera zbiór plików konfiguracyjnych `docker-compose` dla mojego domowego laboratorium (HomeLab).
Większość usług jest uruchamiana na **Raspberry Pi 5** oraz routerze **GL.iNet Flint 2**, tworząc spójny ekosystem do zarządzania siecią, multimediami i automatyką domową.

## 📂 Struktura i Kategorie Usług

Poniżej znajduje się spis usług dostępnych w tym repozytorium, podzielony na kategorie funkcjonalne.

### 🌐 Sieć i Bezpieczeństwo (Network & Security)
Podstawowe usługi zapewniające bezpieczeństwo, dostęp zdalny i blokowanie reklam.

| Usługa | Plik Compose | Opis |
| :--- | :--- | :--- |
| **Nginx Proxy Manager** | `docker-compose_npm.yaml` | Zarządzanie certyfikatami SSL i Reverse Proxy dla wszystkich usług. |
| **AdGuard Home** | `docker-compose_adguard.yaml` | Serwer DNS z blokowaniem reklam i śledzenia w całej sieci. |
| **Vaultwarden** | `docker-compose_vaultwarden.yaml` | Lekki serwer Bitwarden do bezpiecznego zarządzania hasłami. |
| **Glass / DHCP** | `docker-compose_glass-dhcp.yaml` | Serwer DHCP / Zarządzanie adresacją IP. |

### ☁️ Chmura Osobista i Backup (Cloud & Storage)
Przechowywanie danych, synchronizacja plików i kopie zapasowe.

| Usługa | Plik Compose | Opis |
| :--- | :--- | :--- |
| **Nextcloud** | `docker-compose_nextcloud.yaml` | Prywatna chmura do plików, kalendarza i kontaktów. |
| **Syncthing** | `docker-compose_syncthing.yaml` | Synchronizacja plików P2P między urządzeniami. |
| **Duplicati** | `docker-compose_duplicati.yaml` | Automatyczne, szyfrowane kopie zapasowe danych. |
| **JDownloader 2** | `docker-compose_JDownloader2.yaml` | Menedżer pobierania plików obsługiwany przez przeglądarkę. |

### 📺 Media i Rozrywka
Centrum multimedialne.

| Usługa | Plik Compose | Opis |
| :--- | :--- | :--- |
| **Jellyfin** | `docker-compose_jellyfin.yaml` | Serwer mediów (filmy, seriale) - alternatywa dla Plex/Emby. |

### 📊 Monitoring i Narzędzia (Monitoring & Tools)
Utrzymanie zdrowia serwera i powiadomienia.

| Usługa | Plik Compose | Opis |
| :--- | :--- | :--- |
| **Portainer** | `docker-compose_portainer.yaml` | Graficzny interfejs (GUI) do zarządzania Dockerem. |
| **Uptime Kuma** | `docker-compose_uptime_kuma.yaml` | Monitorowanie dostępności usług (status page). |
| **Speedtest Tracker**| `docker-compose_speedtest_tracker.yaml` | Automatyczne testowanie prędkości łącza i wykresy historii. |
| **Checkmk** | `docker-compose_checkmk.yaml` | Zaawansowany system monitoringu infrastruktury IT. |
| **Diun** | `docker-compose_diun.yaml` | (Docker Image Update Notifier) Powiadomienia o nowych wersjach obrazów. |
| **Gotify** | `docker-compose_gotify.yaml` | Własny serwer powiadomień Push. |
| **Ofelia** | `ofelia/` & `docker-compose_ofelia.yaml` | Scheduler zadań (zamiennik Crona) do zarządzania kontenerami. |
| **Monitoring Stack** | `monitoring/` | Zestaw Prometheus + Grafana do wizualizacji metryk. |

### 🏠 Smart Home i Biuro
Automatyka i praca.

| Usługa | Plik Compose | Opis |
| :--- | :--- | :--- |
| **Node-RED** | `docker-compose_node_red.yaml` | Narzędzie do łączenia urządzeń sprzętowych, API i usług online (automatyzacje). |
| **Collabora** | `docker-compose_collabora.yaml` | Pakiet biurowy online (integracja z Nextcloud). |
| **Firefox** | `docker-compose_firefox.yaml` | Przeglądarka internetowa uruchamiana w kontenerze. |

## 🚀 Jak używać?

Każdy plik YAML jest niezależny (lub stanowi część większego stosu). Aby uruchomić wybraną usługę:

```bash
# Przykład dla AdGuard Home
docker compose -f docker-compose_adguard.yaml up -d

# Przykład dla Portainera
docker compose -f docker-compose_portainer.yaml up -d
