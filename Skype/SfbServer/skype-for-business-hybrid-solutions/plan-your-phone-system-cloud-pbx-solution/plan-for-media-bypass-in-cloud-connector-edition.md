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
description: 請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本來實現媒體旁路的規劃考慮。 如需有關部署媒體旁路的資訊，請參閱在雲端連接器版本中部署媒體旁路。
ms.openlocfilehash: 67598cbe31dac074bf360ba6fe1462544fe12c5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814491"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a>規劃 Cloud Connector Edition 中的媒體旁路
 
請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本來實現媒體旁路的規劃考慮。 如需有關部署媒體旁路的資訊，請參閱[在雲端連接器版本中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)。
  
「媒體旁路」可讓用戶端直接傳送媒體至公用交換式電話網絡（PSTN）的下一個躍點（閘道或會話邊界控制器（SBC）），並從媒體路徑中消除雲端連接器版本元件。
  
媒體旁路可減少延遲、造成資料包遺失的可能性，以及可能失敗的點數，以改善語音品質。 取消繞過呼叫的媒體處理會減少雲端連接器上的負載，這可讓您獲得較高的併發通話次數，而且可以改善可伸縮性。 
  
 從媒體處理工作中釋放雲端連接器可能會減少基礎結構所需的雲端連接器裝置數目，因此您應該盡可能啟用媒體旁路。
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a>媒體旁路如何影響媒體與信號路徑

當信號使用相同的路徑，或沒有媒體旁路時，媒體流程會有所不同。 下列圖表顯示拓撲中的媒體與信號路徑，以及不使用媒體旁路的情況。 
  
例如，在下列拓撲（不會使用媒體旁路）中，商務用 Skype 用戶端會將 PSTN 呼叫加入外部號碼、SIP 信號傳送到 Office 365，而 Office 365 則會根據最終使用者的語音指示信號流量原則. 若是雲端連接器使用者，語音原則會將信號流量導向雲端連接器 Edge 伺服器，然後透過雲端連接器轉送伺服器將信號流量路由到 PSTN 會話邊界控制器（SBC）或閘道。 媒體從商務用 Skype 用戶端傳送到雲端連接器中繼伺服器，然後移至 SBC 或閘道，如下列圖表所示：
  
**沒有媒體旁路的媒體與信號路徑**

![沒有媒體旁路的信號](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
從 PSTN 撥入電話會以相反的方向使用相同的傳送信號路徑。 對於內部使用者，媒體仍會在商務用 Skype 用戶端和雲端連接器中繼伺服器以及 SBC 或閘道之間最終流動。
  
在下一個拓朴中（這會採用媒體旁路），信號會採用相同的路徑，但媒體會直接在商務用 Skype 用戶端與 SBC 或閘道之間流動，如下圖所示：
  
**使用媒體旁路的媒體與信號路徑**

![使用媒體旁路進行信號](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a>多網站案例和媒體旁路

如果您想要使用單一雲端連接器裝置將電話語音提供給多個網站，則媒體旁路也很有用。 因為雲端連接器無法根據來源或目的地號碼來傳送呼叫，所以大部分的企業都會將 SBC 或閘道部署在雲端連接器背後，以作出路由決定。 在這種情況下，媒體旁路會消除用戶端與中央 SBC 或閘道之間的跳躍，如下圖所示：
  
**多網站應用程式**

![雲端連接器多網站範例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. SIP 流量會從蘇黎世中的使用者流向 Office 365。
    
2. 然後，通訊會按照使用者語音路由策略中指定的阿姆斯特丹，路由到雲端連接器裝置。
    
3. [阿姆斯特丹] 中的雲端連接器裝置會將 SIP 流量，以阿姆斯特丹傳送給中央閘道。
    
4. [阿姆斯特丹] 中的中央閘道會建立適當的路由決定，然後將流量傳送到蘇黎世中的 SBC 或閘道，而媒體則會直接在商務用 Skype 用戶端和 SBC 或閘道的阿姆斯特丹之間流動。
    
   這個方法可讓您在每一個雲端連接器部署中，以多個使用者為中心介面提供更多使用者。 即使已從媒體路徑中消除雲端連接器，在集中式多網站案例中，媒體仍可能會根據所需的兩倍來進行，以流過集中的 SBC 或閘道。
  
如果用戶端位於公司網路外部的外部通話中，媒體流量會透過來自于雲端連接器的邊緣和轉送伺服器以及蘇黎世與阿姆斯特丹之間的 WAN 連結來流動，如下圖所示：
  
![雲端連接器多網站範例2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a>媒體略過支援的用戶端

在第一次使用媒體旁路的情況下，唯一支援的用戶端就是 Office 365 專業增強版、版本16.0.7870.2020 或更新版本中的商務用 Skype 2016 Windows 用戶端。 客戶可以使用任何通道： [目前]、[已推遲] 或 [第一次發行]。 
  
> [!NOTE]
> 如果您使用的是用戶端 VPN 解決方案與商務用 Skype 用戶端，則只有 VPN 分割隧道設定支援媒體略過。 
  
如需發行通道的詳細資訊，請參閱[Office 365 專業增強版更新通道的概覽](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
針對不同通道中的目前發行版本用戶端，請參閱[Office 365 專業增強版更新的版本資訊](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)。 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a>媒體略過的雲端連接器容量考慮

如果沒有媒體旁路，且視硬體而定，雲端連接器裝置可以處理從50到500同時進行的呼叫，需要透過中繼伺服器傳送媒體。 如需詳細資訊，請參閱[規劃商務用 Skype 雲端連接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
在啟用媒體旁路的情況下，支援的版本上的內部用戶端不使用中繼伺服器，因此內部用戶端數量可能會大幅增加。 
  
如上所述，外部用戶端或不受支援的用戶端將會使用雲端連接器邊緣和媒體的中繼伺服器。 計算網站中應該放置多少雲端連接器裝置的時間時，您必須考慮來自外部使用者與不受支援之用戶端的使用者的流量。
  
## <a name="cloud-connector-supports-always-bypass-mode"></a>雲端連接器支援 Always 旁路模式

雲端連接器只支援 [總是略過模式]。 在內部部署環境中，有兩種選項可供選擇：總是略過並使用網站和區域資訊。
  
[永遠繞過] 表示系統會嘗試對內部用戶端的所有 PSTN 呼叫進行媒體略過，成為來源或目的地點。 若要判斷用戶端是否為內部或外部用戶端，則會使用中繼伺服器虛擬機器上的網站。 如果用戶端可以存取該網站，就會將它視為內部，並使用媒體略過。 如果用戶端無法存取該網站（例如，用戶端位於家用網路上），則不會使用媒體旁路。 
  
Always 旁路在使用者與 PSTN 網站內的 PSTN 閘道之間必須有障礙的連線性。 
  
如需詳細資訊，請參閱[規劃商務用 Skype 雲端連接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。 
  
例如，在下圖中，歐洲使用者必須與三個會話邊界控制器（SBCs）以阿姆斯特丹的方式連接，而我們的西部使用者必須在西雅圖的兩個半形中正確連接。 [良好連接] 表示它們位於與 SBCs 或閘道相同的網路網站，或位於具備適當頻寬的 WAN 連結上。
  
![雲端連接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> 如果從蘇黎世的使用者移至西雅圖辦公室，而您想要使用內部網路來傳送來自歐洲的旅遊使用者和閘道之間的媒體流量（而不是透過網際網路），您必須確認西雅圖辦公室和阿姆斯特丹歐洲的 [SBCs] 或 [閘道] 的 office 位於 [符合良好的連線]。 
  
## <a name="codecs-used-in-media-bypass"></a>在媒體旁路中使用的編解碼器

在啟用媒體旁路的情況下，用戶端與 SBC 或閘道之間的媒體流量會使用711編解碼器。 
  
## <a name="see-also"></a>另請參閱

[在雲端連接器版本中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)
