# 🏗️ Home Lab Hardware Inventory

## 🚀 Dell PowerEdge R610

> **Role:** Proxmox Node

- **CPU:** 2x Intel(R) Xeon(R) X5570 @ 2.93GHz (16 Threads Total)
    
- **RAM:** 48 GB DDR3 ECC @ 1333 MHz
    
- **Storage Controller:** SVNXINGTII 9211-8I (IT Mode) 6Gbps SAS
    
- **Storage (Tank):** 5x Dell 1.2TB 10K 12GB/s SAS 2.5"
    
    - **Configuration:** RAIDZ1 (~4.65 TB Usable)
        
- **Boot Drive:** Patriot Memory P220 256GB SSD
    
- **Power:** 2x 717W Redundant Energy Smart PSUs
    

---

## 🏛️ Dell PowerEdge R710

> **Role:** Proxmox Node

- **CPU:** 2x Intel(R) Xeon(R) X5570 @ 2.93GHz (16 Threads Total)
    
- **RAM:** 96 GB DDR3 ECC @ 1333 MHz
    
- **Storage Controller:** SVNXINGTII 9211-8I (IT Mode) 6Gbps SAS
    
- **Storage (Tank):** 6x HGST 3TB 7.2K 6GB/s SAS 3.5"
    
    - **Configuration:** RAIDZ2 (~11.84 TB Usable)
        
- **Boot Drive:** X12_SSD_256GB
    
- **Power:** 2x 870W Redundant Energy Smart PSUs
    

---

## 🛡️ Dell Optiplex 3050

> **Role:** Proxmox Backup Server (PBS)

- **CPU:** Intel Core i5-7500 @ 3.4GHz (4C/4T - 3.8GHz Turbo)
    
- **RAM:** 32 GB
    
- **Form Factor:** Mini-Tower (MT)
    
- **Note:** Dedicated to deduplicated backups for the R610 and R710 nodes.
    

---

## 🎮 Aorus PC

> **Role:** Gaming & Local AI Inference

- **CPU:** Intel Core i5-11600K @ 3.9GHz (6C/12T - 4.9GHz Turbo)
    
- **RAM:** 32 GB
    
- **GPU:** NVIDIA RTX 5070 Ti