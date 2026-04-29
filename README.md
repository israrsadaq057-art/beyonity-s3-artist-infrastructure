# BEYONITY S3 ARTIST INFRASTRUCTURE

## PROJECT OVERVIEW

Complete AWS S3 infrastructure for 20 artists at Beyonity, a 3D animation studio.

## IT AND NETOWRK ADMINISTRATOR

- **Name:** Israr Sadaq
- **Email:** israrsadaq057@gmail.com
- **AWS Account:** 945504685795
- **Region:** us-east-1

## INFRASTRUCTURE COMPONENTS

### S3 BUCKETS (5 TOTAL)

| Bucket Name | Purpose |
|-------------|---------|
| `beyonity-3d-assets-prod-945504685795` | Production 3D assets |
| `beyonity-backups-945504685795` | Daily automated backups |
| `beyonity-client-share-945504685795` | Secure client file sharing |
| `beyonity-logs-945504685795` | Access logs and inventory |
| `beyonity-test-bucket-945504685795` | Testing environment |

### ARTIST FOLDERS (20 ARTISTS)

```

artists/
├── anna/
├── ben/
├── carla/
├── david/
├── elena/
├── felix/
├── grace/
├── henry/
├── irena/
├── jonas/
├── karla/
├── lukas/
├── mona/
├── niklas/
├── olivia/
├── paul/
├── quinn/
├── rachel/
├── stefan/
└── tina/

```

Each artist folder contains:
- `active/models/` - 3D model files
- `active/textures/` - Texture files
- `active/renders/` - Final renders
- `wip/` - Work in progress (auto-delete after 14 days)
- `archive/` - Completed work (moves to Glacier after 30 days)

### PROJECT FOLDERS (4 PROJECTS)

```
projects/
├── Project-Apex/
│ ├── models/
│ ├── textures/
│ ├── renders/
│ └── final/
├── Project-Nexus/
├── Project-Omega/
└── Project-Virtua/

```
### SHARED ASSET FOLDERS

```
shared/
├── textures/ # Shared texture library
├── models/ # Shared model library
├── hdri/ # HDRI environments
└── plugins/ # Shared tools and plugins

```

## FEATURES ENABLED

| Feature | Status | Purpose |
|---------|--------|---------|
| Versioning | `ENABLED` | Recover deleted files |
| Transfer Acceleration | `ENABLED` | 50-500% faster uploads |
| HTTPS Enforcement | `ACTIVE` | Secure access only |
| Public Access Block | `ENABLED` | All buckets private |
| Server Side Encryption | `AES-256` | Data at rest encryption |

## LIFECYCLE RULES

| Rule ID | Target | Action | Timeframe |
|---------|--------|--------|-----------|
| `DeleteWIPAfter14Days` | `wip/` folder | Delete | 14 days |
| `ArchiveAfter30Days` | `archive/` folder | Move to Glacier | 30 days |
| `DeleteClientSharesAfter7Days` | `client_shares/` | Delete | 7 days |
| `DeleteTempFilesAfter1Day` | `temp/` folder | Delete | 1 day |

## MONITORING CONFIGURATION

### CloudWatch Alarms

| Alarm Name | Threshold | Action |
|------------|-----------|--------|
| `Beyonity-Production-Bucket-Size-Alarm` | > 3 TB | Email alert |
| `Beyonity-High-Request-Rate` | > 1000 per hour | Email alert |
| `Beyonity-High-Error-Rate` | > 10 per hour | Email alert |

### SNS Email Alerts

- **Topic:** `BeyonityS3Alerts`
- **Subscriber:** `israrsadaq057@gmail.com`
- **Status:** Confirmed

### S3 Inventory

- **Frequency:** Daily
- **Format:** CSV
- **Destination:** `beyonity-logs/inventory/`
- **Fields:** Size, LastModifiedDate, StorageClass, ETag

### Server Access Logging

- **Target Bucket:** `beyonity-logs-945504685795`
- **Prefix:** `access-logs/`

## Screenshots

### S3-Buckets

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/582b909b-3949-4ca7-83ad-216f473e22af" />

### Artists

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1f553828-2d32-44f2-b5c4-29e9a2650b9c" />

### Projects

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/56e0ec27-144e-4eef-964f-e80b48eb1108" />

### S3-Monitring Dashboard

<img width="1920" height="1080" alt="S3_Monitring_dashboard" src="https://github.com/user-attachments/assets/f54784e2-a598-4982-b35f-f99d35125673" />

### S3-Monitring Verification

<img width="1920" height="1080" alt="montring_verification" src="https://github.com/user-attachments/assets/1e369704-99d5-468e-af31-ce3f29828b87" />

### Infrastructure Verification

<img width="1920" height="1080" alt="infrastructure_Verification" src="https://github.com/user-attachments/assets/48fd388d-cba4-4b59-8b25-82cb8fc37d3a" />

### Storage Summary

<img width="1920" height="1080" alt="storage_summery" src="https://github.com/user-attachments/assets/7d10021b-807a-42b7-87cf-69c773a78c3b" />

### Folder Verification

<img width="1920" height="1080" alt="verify_folder" src="https://github.com/user-attachments/assets/e4498035-b184-49c4-acd3-a767c040ff67" />








  
