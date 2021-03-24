---
title: 在 Cloud Connector 中部署多個網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 瞭解如何在雲端連接器 Edition 中部署多個 PSTN 網站。
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098399"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>在 Cloud Connector 中部署多個網站

> [!Important] 
> 雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。 當您的組織升級至小組後，請瞭解如何使用 [直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。

瞭解如何在雲端連接器 Edition 中部署多個 PSTN 網站。
  
本節說明如何在多部公用交換電話網路 (PSTN) 網站上進行部署。 使用與部署單一網站相同的步驟，一次部署一個網站。 本主題說明多個網站部署中的網站之間的考慮和差異。 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>多部公用交換電話網路 (PSTN) 網站

下列示範設定部署不同 PSTN 網站之商務用 Skype 雲端連接器 Edition 的範例設定。 在您開始部署之前，請確定您的設定設定正確無誤。
  
PSTN 網站1
  
```console
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

PSTN Site 2
  
```console
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

針對您要新增的每個 PSTN 網站，依照在 [雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)中的步驟進行。
  
> [!IMPORTANT]
> 準備高可用性的共用資料夾 (的 HA) 是每個 PSTN 網站。 PSTN 網站之間的共用資料夾 **必須** 不同。 請勿對多個網站使用同一個共用資料夾。 > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>與多網站部署相比，具有高可用性的單一網站 (HA) 
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

下表列出具有 HA 支援的單一網站與多個網站部署之間的差異。
  
|**類別**|**項目**|**具有高可用性的單一網站**|**多網站**|
|:-----|:-----|:-----|:-----|
|設定  <br/> |裝置主機名稱 <br/> |各裝置 **不同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |共用資料夾  <br/> |跨裝置需要 **相同** 的共用資料夾 <br/> |需要跨裝置使用 **不同** 的共用資料夾 <br/> |
|設定  <br/> |VirtualMachineDomain  <br/> |需要跨裝置的 **相同** 網域 <br/> |需要跨 PSTN 網站的 **相同** 網域 <br/> |
|設定  <br/> |SIPDomains  <br/> |跨裝置的功能變數名稱和順序應該 **相同** <br/> |各 PSTN 網站的功能變數名稱和順序應該 **相同** <br/> |
|設定  <br/> |網站名稱  <br/> |**相同** 跨裝置的網站名稱 <br/> |**不同** PSTN 網站上的網站名稱 <br/> |
|設定  <br/> |伺服器名稱  <br/> |各裝置 **不同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |內部集區 Fqdn  <br/> |跨裝置 **相同** <br/> |跨 PSTN 網站 **相同** <br/> |
|設定  <br/> |內部 Ip  <br/> |各裝置 **不同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |外部 FQDN  <br/> |跨裝置 **相同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |外部 Ip  <br/> |各裝置 **不同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |PSTN GW 設定  <br/> |跨裝置 **相同** <br/> |各 PSTN 網站 **不同** <br/> |
|設定  <br/> |DNS 記錄  <br/> |新增具有 **相同** 外部存取 fqdn 和 **不同** IP 位址的記錄 <br/> |使用 **不同** 的外部存取 fqdn 和 **不同** 的 IP 位址新增記錄 <br/> |
|設定  <br/> |混合租使用者  <br/> |設定 HybridPSTNSite  <br/> 設定 PeerDestination 為 fallback  <br/> |設定 HybridPSTNSite  <br/> 設定 PeerDestination 為 fallback  <br/> |
|設定  <br/> |閘道  <br/> |此網站中的 MS GW **M:N** 對應 <br/> |PSTN 閘道 (s) 在每個 PSTN 網站中應該只連接至相同網站的轉送伺服器 (s)   <br/> |
|設定  <br/> |User  <br/> |設定 UserPSTNSettings  <br/> |設定 UserPSTNSettings  <br/> |
