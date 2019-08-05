---
title: 在雲端連接器中部署多個網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 瞭解如何在雲端連接器版本中部署多個 PSTN 網站。
ms.openlocfilehash: ba6b76366b65a9febb9fab06e7cfb0fad759e5ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190846"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>在雲端連接器中部署多個網站
 
瞭解如何在雲端連接器版本中部署多個 PSTN 網站。
  
本節說明如何部署多個公用交換電話網絡 (PSTN) 網站。 使用與部署單一網站相同的步驟, 一次部署一個網站。 本主題說明多重網站部署中的網站與差異的考慮。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>多個公用交換電話網絡 (PSTN) 網站

下列顯示部署不同 PSTN 網站之商務用 Skype 雲端連接器版的範例配置。 開始部署前, 請確定您的設定正確無誤。
  
PSTN 網站1
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

PSTN 網站2
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

針對您要新增的每個 PSTN 網站, 按照在[雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)中的步驟進行。
  
> [!IMPORTANT]
> 針對每個 PSTN 網站準備高可用性 (HA) 的共用資料夾。 在 PSTN 網站之間, 共用資料夾**必須**不同。 請勿對多個網站使用相同的共用資料夾。 > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>高可用性 (HA) 與多網站部署的單一網站
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

下表列出單一網站與 HA 支援及多重網站部署之間的差異。
  
|**類別**|**選項**|**含 HA 的單一網站**|**多網站**|
|:-----|:-----|:-----|:-----|
|設定  <br/> |裝置主機名稱 <br/> |跨多個裝置**不同** <br/> |跨 PSTN 網站**不同** <br/> |
|Setup.exe  <br/> |共用資料夾  <br/> |在多個裝置上需要**相同**的共用資料夾 <br/> |跨裝置需要**不同**的共用資料夾 <br/> |
|設定  <br/> |VirtualMachineDomain  <br/> |跨裝置需要**相同**的網域 <br/> |在 PSTN 網站上需要**同一個**網域 <br/> |
|設定  <br/> |SIPDomains  <br/> |網功能變數名稱稱和順序在各個裝置中應該是**相同**的 <br/> |網功能變數名稱稱和順序在 PSTN 網站中應該是**相同**的 <br/> |
|設定  <br/> |網站名稱  <br/> |**相同**跨裝置的網站名稱 <br/> |**不同**PSTN 網站上的網站名稱 <br/> |
|設定  <br/> |伺服器名稱  <br/> |跨多個裝置**不同** <br/> |跨 PSTN 網站**不同** <br/> |
|設定  <br/> |內部池 Fqdn  <br/> |跨裝置**相同** <br/> |跨 PSTN 網站**相同** <br/> |
|設定  <br/> |內部 Ip  <br/> |跨多個裝置**不同** <br/> |跨 PSTN 網站**不同** <br/> |
|設定  <br/> |外部 FQDN  <br/> |跨裝置**相同** <br/> |跨 PSTN 網站**不同** <br/> |
|設定  <br/> |外部 Ip  <br/> |跨多個裝置**不同** <br/> |跨 PSTN 網站**不同** <br/> |
|設定  <br/> |PSTN GW 設定  <br/> |跨裝置**相同** <br/> |跨 PSTN 網站**不同** <br/> |
|設定  <br/> |DNS 記錄  <br/> |使用**相同**的外部存取 fqdn 和**不同**的 IP 位址新增記錄 <br/> |新增具有**不同**外部存取 fqdn 及**不同**IP 位址的記錄 <br/> |
|Setup.exe  <br/> |混合式租使用者  <br/> |設定 HybridPSTNSite  <br/> 設定 PeerDestination 以進行回退  <br/> |設定 HybridPSTNSite  <br/> 設定 PeerDestination 以進行回退  <br/> |
|Setup.exe  <br/> |關  <br/> |此網站中的 MS GW **M:N**對應 <br/> |每個 PSTN 網站中的 PSTN 閘道應該只會連線到相同網站中的中繼伺服器 (s)  <br/> |
|Setup.exe  <br/> |使用者名  <br/> |設定 UserPSTNSettings  <br/> |設定 UserPSTNSettings  <br/> |
   

