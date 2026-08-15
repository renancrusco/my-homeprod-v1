# 🏠 My HomeProd - Homelab

> Configurações e infraestrutura do meu homelab pessoal

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Docker](https://img.shields.io/badge/docker-✓-blue)
![Git](https://img.shields.io/badge/git-✓-orange)

---

## 📋 Sobre

Este repositório contém todas as configurações do meu homelab, incluindo:

- **Serviços de Mídia**: Jellyfin, Jellyseerr
- **Suite ARR**: Sonarr, Radarr, Bazarr, Prowlarr
- **Download**: qBittorrent
- **DNS/Ad-Block**: AdGuard Home
- **Dashboard**: Homepage
- **Música**: Navidrome
- **Gerenciamento**: Portainer
- **CMS**: Reactive Resume

## 🏗️ Estrutura do Projeto

```
homelab/
├── docker-compose.yml               # Orquestrador principal
├── .env.example                     # Template de variáveis de ambiente
├── .gitignore                       # Arquivos ignorados pelo Git
├── README.md                        # Documentação principal
│
├── configs/                         # Configurações dos serviços
│   ├── adguard-config/
│   │   ├── conf/
│   │   │   └── AdGuardHome.yaml
│   │   └── work/                    # Dados (ignorado)
│   │
│   ├── bazarr-config/
│   │   ├── config/
│   │   │   └── *.yaml, *.yml, *.json
│   │   ├── backup/                  # Dados (ignorado)
│   │   ├── db/                      # Dados (ignorado)
│   │   └── log/                     # Dados (ignorado)
│   │
│   ├── homepage-config/
│   │   ├── custom.css
│   │   ├── custom.js
│   │   ├── images/
│   │   └── logs/                    # Dados (ignorado)
│   │
│   ├── jellyfin-config/             # Configurações do Jellyfin
│   │
│   ├── jellyseerr-config/           # Configurações do Jellyseerr
│   │
│   ├── navidrome/
│   │   └── data/                    # Dados (ignorado)
│   │
│   ├── portainer-data/              # Dados (ignorado)
│   │
│   ├── prowlarr-config/
│   │   ├── config.xml
│   │   ├── Backups/                 # Dados (ignorado)
│   │   ├── logs/                    # Dados (ignorado)
│   │   └── *.db*                    # Dados (ignorado)
│   │
│   ├── qbittorrent-config/          # Configurações do qBittorrent
│   │
│   ├── radarr-config/               # Configurações do Radarr
│   │
│   ├── reactive-resume/
│   │   └── postgres/                # Dados (ignorado)
│   │
│   └── sonarr-config/               # Configurações do Sonarr
│
├── scripts/                         # Scripts de automação
│   ├── backup.sh
│   ├── restore.sh
│   └── healthcheck.sh
│
├── docs/                            # Documentação adicional
│   ├── SETUP.md
│   ├── SERVICES.md
│   └── MIGRATION.md
│
└── volumes/                         # Volumes Docker (ignorado)
    └── ...
```

## 🛠️ Serviços e Portas

| Serviço | Porta | Descrição |
|---------|-------|-----------|
| **AdGuard Home** | `53`, `3000` | DNS Ad-blocker |
| **Jellyfin** | `8096` | Media Server |
| **Seerr** | `5055` | Gerenciador de requests |
| **Sonarr** | `8989` | Gerenciador de séries |
| **Radarr** | `7878` | Gerenciador de filmes |
| **Bazarr** | `6767` | Legendas |
| **Prowlarr** | `9696` | Indexador de torrents |
| **Flaresolverr** | `8191` | DNS parasuite 'ARR |
| **qBittorrent** | `8080` | Cliente Torrent |
| **Homepage** | `8090` | Dashboard |
| **Navidrome** | `4533` | Servidor de música |
| **Portainer** | `9443` | Gerenciador Docker |
| **Glance** | `8081` | Painel de monitoramento |
| **Reactive Resume** | `3002` | Gerador de currículos |
| **Samba** | `139`,`445` | Gerador de currículos |

---

## 🚀 Como Usar

### Pré-requisitos

- Docker e Docker Compose
- Git

### Passos

```bash
# 1. Clone o repositório
git clone https://github.com/renancrusco/my-homeprod-v1.git
cd my-homeprod-v1

# 2. Configure as variáveis de ambiente
cp .env.example .env
# Edite o .env com suas credenciais

# 3. Inicie os serviços
docker-compose up -d

# 4. Verifique se tudo está rodando
docker-compose ps