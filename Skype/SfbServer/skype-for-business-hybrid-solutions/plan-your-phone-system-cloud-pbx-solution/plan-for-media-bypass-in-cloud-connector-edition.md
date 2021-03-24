---
title: 規劃 Cloud Connector Edition 中的媒體旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 閱讀此主題以查看使用雲端連接器 Edition 版本2.0 和更新版本執行媒體旁路的規劃考慮。 如需部署媒體旁路的詳細資訊，請參閱在雲端連接器 Edition 中部署媒體旁路。
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096197"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>規劃 Cloud Connector Edition 中的媒體旁路
 
閱讀此主題以查看使用雲端連接器 Edition 版本2.0 和更新版本執行媒體旁路的規劃考慮。 如需部署媒體旁路的詳細資訊，請參閱 [在雲端連接器 Edition 中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)。
  
媒體旁路可讓用戶端直接將媒體傳送到公用交換電話網路 (PSTN) 下一個躍點（閘道或會話邊界控制器 (SBC) ），並從媒體路徑中消除雲端連接器版本元件。
  
媒體旁路可減少延遲、封包遺失的可能性，以及可能失敗的點數，以改善語音品質。 取消略過通話的媒體處理會減少雲端連接器上的負載，使並行通話數量變得更高，而且可提高可擴充性。 
  
 從媒體處理工作中釋放 Cloud Connector 可能會減少基礎結構所需的雲端連接器裝置數目，所以應盡可能啟用媒體旁路。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒體旁路如何影響媒體和信號路徑

當信號使用或不具有媒體旁路的相同路徑時，媒體流程會有所不同。 下列圖表顯示使用和不使用媒體旁路的拓撲中的媒體和信號路徑。 
  
例如，在下列拓撲中（不採用媒體旁路）：商務用 Skype 用戶端將 PSTN 通話加入外部號碼，SIP 信號會移至 Microsoft 365 或 Office 365，這會根據使用者語音原則來指示信號流量。 對於 Cloud Connector 使用者，語音原則會將信號流量指引至雲端連接器 Edge Server，然後透過雲端連接器轉送伺服器將信號流量路由傳送至 PSTN 會話邊界控制器 (SBC) 或閘道。 媒體會從商務用 Skype 用戶端傳送至雲端連接器轉送伺服器，然後再流向 SBC 或閘道，如下圖所示：
  
**沒有媒體旁路的媒體和信號路徑**

![沒有媒體旁路的信號](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
從 PSTN 傳入的呼叫會以相反方向使用相同的信號路徑。 針對內部使用者，媒體仍會在商務用 Skype 用戶端和雲端連接器轉送伺服器之間流動，然後是 SBC 或閘道。
  
在下一個拓撲中（會使用媒體旁路）-信號會採用相同的路徑，但媒體會直接在商務用 Skype 用戶端與 SBC 或閘道之間流動，如下列圖表所示：
  
**媒體和使用媒體旁路的信號路徑**

![使用媒體旁路的信號](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多網站案例和媒體旁路

當您想要使用單一雲端連接器裝置，將電話語音服務提供給多個網站時，媒體旁路也十分實用。 因為雲端連接器無法根據來源或目的地號碼來路由呼叫，所以大多數的企業都會將 SBC 或閘道部署在雲端連接器背後，以進行路由決策。 在此案例中，媒體旁路會消除用戶端與中央 SBC 或閘道之間的躍點，如下圖所示：
  
**多網站應用程式**

![Cloud Connector Multisite 範例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 流量會從蘇黎世的使用者流向 Microsoft 365 或 Office 365。
    
2. 然後，流量會依照使用者語音路由原則中所指定的阿姆斯特丹，路由傳送至雲端連接器裝置。
    
3. 在阿姆斯特丹中的雲端連接器裝置會將 SIP 流量傳送至中央閘道，單位為阿姆斯特丹。
    
4. 位於阿姆斯特丹的中央閘道會進行適當的路由決策，然後將流量傳送至位於蘇黎世的 SBC 或閘道，而媒體會直接在商務用 Skype 用戶端和 SBC 或閘道之間流動。
    
   這種方法可讓您在每一個雲端連接器部署中為多個使用者服務提供更多使用者。 即使從媒體路徑中消除雲端連接器，在集中式的多網站案例中，也可能會根據需要將 WAN 傳遞到兩倍，以流過集中式 SBC 或閘道。
  
如果用戶端在公司網路外部進行撥出電話，則媒體流量會透過 Cloud Connector 的 Edge 和轉送伺服器，以及蘇黎世和阿姆斯特丹間的 WAN 連結來流動，如下列圖表所示：
  
![Cloud Connector Multisite 範例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>支援的媒體旁路用戶端

使用第一次發行的媒體旁路時，唯一支援的用戶端是商務用 Skype 2016 Windows 用戶端，其為企業版、版本16.0.7870.2020 或更新版本的 Microsoft 365 應用程式的一部分。 客戶可以使用任何通道： Current、延期或 First Release 延期。 
  
> [!NOTE]
> 如果您使用的是用戶端 VPN 方案，並結合商務用 Skype 用戶端，則只有 VPN 分割隧道設定支援媒體旁路。 
  
如需發行通道的詳細資訊，請參閱 [適用于企業的 Microsoft 365 應用程式更新通道](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
如需不同通道之用戶端的目前發行版本本資訊，請參閱適用 [于企業的 Microsoft 365 應用程式更新版本資訊](/officeupdates/release-notes-office365-proplus)。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>媒體旁路的雲端連接器容量考慮

沒有媒體旁路，而且視硬體而定，雲端連接器裝置可以處理從50到500同時通話，以要求透過轉送伺服器進行媒體傳送。 如需詳細資訊，請參閱 [Plan For 商務用 Skype Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md)。 
  
啟用媒體旁路時，支援的版本上的內部用戶端不會使用轉送伺服器，因此內部用戶端的數目會大幅增加。 
  
如以上所述，外部用戶端或不受支援的用戶端將使用雲端連接器 Edge 和轉送伺服器進行媒體。 計算網站中應放入多少雲端連接器裝置時，您必須考慮來自外部使用者的流量和不受支援之用戶端的使用者。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>雲端連接器支援 Always 旁路模式

雲端連接器只支援 Always 略用模式。 在內部部署環境中，有兩種選擇：永遠略過和使用網站與地區資訊。
  
Always 旁路表示對內部用戶端的所有 PSTN 來電嘗試媒體旁路，以作為原始或目的地點。 若要判斷用戶端是否為內部或外部用戶端，則使用轉送伺服器虛擬機器上的網站。 如果用戶端可以到達網站，則會將它視為內部和媒體旁路使用。 如果用戶端無法到達網站 (例如，用戶端位於家用網路) 上，就不會使用媒體旁路。 
  
Always 旁路要求使用者與 PSTN 網站中的 PSTN 閘道之間有沒有障礙的連線能力。 
  
如需詳細資訊，請參閱 [Plan For 商務用 Skype Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md)。 
  
例如，在下圖中，歐洲使用者必須順利連線至三個會話邊界控制器 (SBCs) 在阿姆斯特丹中，我們的西部使用者必須順利連接至西雅圖的兩個 SBCs。 已正確連接表示它們是位於與 SBCs 或閘道相同的網站，或透過具有適當頻寬的 WAN 連結。
  
![雲端連接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果來自蘇黎世的使用者已前往西雅圖 office，而您想要使用內部網路來傳遞 (歐洲的旅行使用者與閘道之間的媒體流量，而不是透過網際網路) ，則必須確定西雅圖 office 和阿姆斯特丹 office 所在的歐洲 SBCs 或閘道已正確連接。 
  
## <a name="codecs-used-in-media-bypass"></a>媒體旁路中使用的編解碼器

啟用媒體旁路時，用戶端與 SBC 或閘道之間的媒體流量會使用 g.711 編解碼器。 
  
## <a name="see-also"></a>另請參閱

[在雲端連接器 Edition 中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)