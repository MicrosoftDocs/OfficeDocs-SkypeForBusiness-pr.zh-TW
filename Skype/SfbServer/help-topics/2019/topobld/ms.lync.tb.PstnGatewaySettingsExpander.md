---
title: PSTN 閘道設定展開工具
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 若要編輯或修改公用交換電話網路 (PSTN) 閘道的設定，請修改下列欄位：
---

# <a name="pstn-gateway-settings-expander"></a>PSTN 閘道設定展開工具
 
若要編輯或修改公用交換電話網路 (PSTN) 閘道的設定，請修改下列欄位：
  
閘道 FQDN 或 IP 位址是必要的項目，並定義 PSTN 閘道的 [完整網域名稱 (FQDN)] 是依網域名稱系統 (DNS) 主機 (A) 記錄、靜態 HOSTS 檔案項目，或 PSTN 閘道的 IP 位址來定義。
  
[SIP 傳輸通訊協定] 可以是傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS)。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。
  
選取是否針對閘道啟用 IPv4 和 IPv6。
  
[其他媒體 IP 位址] 是中繼伺服器適用的定義，表示部署的 PSTN 閘道用於媒體流量的 IP 位址與預設 IP 位址 (通常專用於 SIP 流量) 不同。如果您定義此參數，則 PSTN 閘道支援針對媒體使用不同的網路介面或路徑。如果此位址保留空白，則 PSTN 閘道不支援針對媒體使用替代路徑。
  

