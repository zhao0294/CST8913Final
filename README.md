# CST8913Final

Azure Traffic Manager
=====================
(全球负载均衡 & 故障转移)
        |
        ▼
Azure Front Door
==================
        |
        ▼
+------------------+---------------------+------------------+------------------+
|                  |                     |                  |                  |
| EC VNet          | Kubernetes           | ERP & DB VNet     | Data & BI VNet   |
| (E-Commerce)     | (AKS Pods)           | (敏感数据存储)    | (Power BI)       |
|                  |                     |                  |                  |
| EC App           | Pods (Financial)     | Sensitive DB      | Power BI         |
| Load Balancer    | Pods (Inventory)     | Azure DB MI       | Blob Storage     |
| VM (Web)         | Pods (Front)         | Azure DB ECA      | Azure Backup     |
|                  | Azure DB ERP         | Key Vault         | Archive Storage  |
+------------------+---------------------+------------------+------------------+
        |
        ▼
Application VNet
==================
(后台服务)
Function App
Logic App
        |
        ▼
Hub VNet
========
(核心管理)
Azure AD
Azure DNS
Firewall
Policy & Insights
Monitor
VPN Gateway
        |
        ▼
Azure Site Recovery
===================
(灾难恢复 & 备份管理)
- 保护 VMs、AKS、DB
- 支持 On-Prem to Azure 备份
- 自动化恢复策略（Runbooks）