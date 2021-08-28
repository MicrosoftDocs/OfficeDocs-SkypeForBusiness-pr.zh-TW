---
title: 規劃商務用 Skype Server 中的企業語音
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 在商務用 Skype Server 中企業語音規劃基礎，包括網站、地區、網站之間的網路連結，以及評估語音使用流量。
ms.openlocfilehash: bfd7d4b1491b83c6ad3ab65836777e805689c21f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618809"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>規劃商務用 Skype Server 中的企業語音
 
在商務用 Skype Server 中企業語音規劃基礎，包括網站、地區、網站之間的網路連結，以及評估語音使用流量。
  
企業語音的部署程式取決於您現有的拓撲、基礎結構，以及您要支援的企業語音功能。 必要的程式取決於您選擇的功能，但是還有其他的規劃考慮，您必須以高層次進行。
  
一般來說，請考慮您要部署的網站類型和數目、每個網站的通話量、每個網站的網路連結類型、連接網站的網路連結類型、您是否想要為每個網站提供冗余及容錯移轉語音功能，以及是否要使用現有的 PBX 裝置。 在您規劃整體商務用 Skype Server 時，應考慮下列事項（如高可用性）。 您會視需要在本節的主題中討論這些考慮。
  
## <a name="sites-and-regions"></a>網站與地區

首先，識別您的拓撲中的網站，您將在其中部署企業語音和這些網站所屬的網路地區。 明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。 就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。 決定要在本機部署閘道的位置，Survivable 分支裝置 (Sba) 部署所在的位置，以及您可以在本機或在中央網站) 設定 SIP 主幹 ( (ITSP) 。
  
## <a name="network-links-between-sites"></a>網站間的網路連結

您也需要考慮您期望在中央網站與其分支網站之間之網路連結的頻寬使用量。 如果您有或想要在網站之間部署彈性的 WAN 連結，建議您在每個分支網站上部署閘道，以提供本機直接向內撥號 (已) 使用者在這些網站上終止。 如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。 如果您沒有可恢復的 WAN 連結，請在分支網站上裝載低於1000的使用者，而且沒有本機訓練有素的商務用 Skype Server 系統管理員，我們建議您在分支網站上部署 Survivable 分支裝置。 如果您在分支網站上主持1000和5000使用者、缺乏彈性的 WAN 連線，且有訓練有素的商務用 Skype Server 管理員，我們建議您在分支網站上部署 Survivable 分支伺服器搭配小型閘道。 如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。
  
## <a name="estimating-voice-usage-and-traffic"></a>評估語音使用方式和流量

Microsoft Lync Server 2013，規劃工具使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。
  
> 針對 **輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。
> 
> 針對 **中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。
> 
> 針對 **重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。
    
接下來的埠數目會決定所需的轉送伺服器和閘道數目。 公用交換電話網路 (PSTN) 閘道，大多數的組織都會考慮從兩個埠的大小部署至多達960埠的範圍。  (甚至會有較大的閘道，但是主要是由電話語音服務提供者使用。 ) 
  
例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>企業語音的元件、功能及選項

如需規劃企業語音部署的詳細資訊，請參閱下列各節。
  
- [商務用 Skype Server 中企業語音所需的元件](components-required-for-enterprise-voice.md)
    
- [在商務用 Skype Server 中規劃 PSTN 連線能力](pstn-connectivity-0.md)
    
- [商務用 Skype Server 中的高級企業語音功能的網路設定](network-settings-for-advanced-features.md)
    
- [在商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)
    
- [在商務用 Skype Server 中規劃緊急服務](emergency-services.md)
    
- [在商務用 Skype 中規劃媒體旁路](media-bypass.md)
    
- [使用商務用 Skype 規劃私人電話線](private-telephone-lines.md)
    
- [規劃商務用 Skype 中的 Location-Based 路由](location-based-routing.md)
    
- [在商務用 Skype 中規劃通話管理功能](call-management-features.md)
    
- [在商務用 Skype Server 中規劃企業語音恢復功能](enterprise-voice-resiliency.md)
    

