---
title: 商務用 Skype Server 中的企業語音方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 商務用 Skype Server 中的企業語音規劃基礎, 包括網站、區域、網站之間的網路連結, 以及估計語音使用方式流量。
ms.openlocfilehash: fdc653404f6b7182086af00e6e788a1d3bd421eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187693"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>商務用 Skype Server 中的企業語音方案
 
商務用 Skype Server 中的企業語音規劃基礎, 包括網站、區域、網站之間的網路連結, 以及估計語音使用方式流量。
  
企業語音的部署程式, 取決於您現有的拓撲、基礎結構, 以及您想要支援的企業語音功能。 所需的程式取決於您所選擇的功能, 但是您必須在高層次進行其他規劃考慮。
  
一般來說, 請考慮您想要部署的網站類型及數量, 以及它們的地理位置、每個網站的通話量、連接網站的網路連結類型, 而無論您是否要為每個使用者提供語音功能的冗余與容錯移轉網站, 以及您是否要使用現有的 PBX 裝置。 在您規劃商務用 Skype Server 作為一個整體時, 必須考慮一些考慮 (例如高可用性)。 如有需要, 我們將在本區段的主題中討論這些考慮。
  
## <a name="sites-and-regions"></a>網站和區域

首先, 請在您的拓撲中找出您要部署企業語音的網站, 以及這些網站所屬的網路區域。 具體來說, 請考慮您將如何提供公用的交換電話網絡 (PSTN) 連線至每個網站。 出於易管理性和後勤原因, 這些網站所屬的區域可以是決定因素。 決定要在本機部署閘道的位置, 將部署 Survivable 分支裝置 (SBAs), 以及您可以將 SIP trunks (本機或在中央網站) 設定為網際網路電話服務提供者 (ITSP)。
  
## <a name="network-links-between-sites"></a>網站之間的網路連結

您也需要考慮您在中央網站與其分支網站之間的網路連結上預期的頻寬使用量。 如果您有或想要在網站之間部署彈性 WAN 連結, 建議您在每個分支網站部署一個閘道, 以針對這些網站上的使用者提供本機直向內撥打電話 (已結束)。 如果您有彈性 WAN 連結, 但 WAN 連結上的頻寬可能受到限制, 請設定該連結的 [呼叫許可控制]。 如果您沒有可復原的 WAN 連結, 請在您的分支網站中主持少於1000個使用者, 而且沒有提供當地訓練有素的商務用 Skype 伺服器管理員, 我們建議您在分支網站上部署 Survivable 分支裝置。 如果您是在分支網站上的1000和5000使用者之間主持、缺乏彈性 WAN 連線, 且有訓練有素的商務用 Skype Server 管理員, 我們建議您在分支網站上部署 Survivable 分支伺服器與小型閘道。 如果您有支援媒體旁路的閘道對等, 也可以考慮在受限制的連結上啟用媒體旁路。
  
## <a name="estimating-voice-usage-and-traffic"></a>評估語音使用方式和流量

Microsoft Lync Server 2013、規劃工具會使用下列度量來估計每個網站的使用者流量, 以及支援該流量所需的埠數。
  
> 對於**輕型流量**(每個使用者每小時一個 PSTN 通話), 請在每個埠上見15個使用者。
> 
> 針對**中型交通**(每位使用者每小時2個 PSTN 通話), 圖10每個埠的使用者數。
> 
> 對於**大量流量**(3 個或更多每個使用者每小時的 PSTN 通話), 請依圖5每個埠的使用者。
    
接下來的埠數會決定要使用的中繼伺服器和閘道數目。 大多陣列織考慮將範圍從2個埠部署到最多960個埠的公用交換電話網絡 (PSTN) 閘道。 (甚至是更大的閘道, 但主要是由電話服務提供者使用。)
  
例如, 有10000使用者和中型交通的組織需要1000埠。 所需的閘道數目會等於由閘道總容量決定所需的埠總數。
  
## <a name="components-features-and-options-of-enterprise-voice"></a>企業語音的元件、功能和選項

如需規劃企業語音部署的詳細資訊, 請參閱下列各節。
  
- [商務用 Skype Server 中的企業語音所需元件](components-required-for-enterprise-voice.md)
    
- [在商務用 Skype Server 中規劃 PSTN 連通性](pstn-connectivity-0.md)
    
- [商務用 Skype Server 中的 [高級企業語音功能] 的網路設定](network-settings-for-advanced-features.md)
    
- [在商務用 Skype Server 中規劃通話許可控制](call-admission-control.md)
    
- [在商務用 Skype Server 中規劃緊急服務](emergency-services.md)
    
- [在商務用 Skype 中規劃媒體旁路](media-bypass.md)
    
- [使用商務用 Skype 規劃私人電話線](private-telephone-lines.md)
    
- [在商務用 Skype 中規劃以位置為基礎的路由](location-based-routing.md)
    
- [規劃商務用 Skype 中的通話管理功能](call-management-features.md)
    
- [商務用 Skype Server 中的企業語音復原方案](enterprise-voice-resiliency.md)
    

