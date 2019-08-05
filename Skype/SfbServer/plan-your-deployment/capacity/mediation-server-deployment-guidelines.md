---
title: 商務用 Skype Server 中的中繼伺服器部署指導方針
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主題描述有關轉送伺服器部署的規劃指導方針。
ms.openlocfilehash: fdfc18871e4aa9ea30d7a02063e7d1a0bc05b6ca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187912"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>商務用 Skype Server 中的中繼伺服器部署指導方針
 
本主題描述有關轉送伺服器部署的規劃指導方針。
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Collocated 或獨立的中繼伺服器？

在預設情況下, 中繼伺服器是在中央網站的 [標準版] 伺服器或 [前端] 池中的 [標準版] 伺服器或 [前端伺服器] 上 collocated。 可處理的公用交換電話網絡 (PSTN) 通話數目, 以及池中所需的電腦數將取決於:
  
- 中繼伺服器池控制的閘道對等數目。
    
- 高容量流量穿過這些閘道。
    
- 呼叫其媒體略過中繼伺服器的通話百分比。
    
規劃時, 請務必考慮 PSTN 通話的媒體處理需求, 以及不支援媒體旁路的 A/V 會議, 以及處理信號互動的處理方式, 以應對需要的繁忙小時數要求受. 如果您沒有足夠的 CPU, 您必須部署一個獨立的中繼伺服器池。 此外, PSTN 閘道、IP-Pbx 和 SBCs 將需要分割為由一個池中的 collocated 轉送伺服器所控制的子集, 以及一個或多個獨立的池中的獨立轉送伺服器。
  
如果您已部署 PSTN 閘道、IP-Pbx 或會話邊界控制器 (SBCs), 但缺乏與中繼伺服器池互動的能力, 就必須將它們與單一轉送伺服器所組成的獨立池建立關聯。 您的 PSTN 閘道、IP-Pbx 或 SBCs 需要做的一些事包括:
  
- 在池中的中繼伺服器上執行網狀圖層網域名稱系統 (DNS) 負載平衡 (或將流量均勻地路由到池中的所有中繼伺服器)。
    
- 接受來自池中任何中繼伺服器的流量。
    
您可以使用商務用 Skype 規劃工具來評估 collocating 的中繼伺服器與您的前端池是否可以處理負載。 如果您的環境無法滿足這些需求, 則您必須部署獨立的中繼伺服器池。
  
## <a name="central-site-and-branch-site-considerations"></a>中心網站與分支網站考慮

 中央網站上的中繼伺服器可用於傳送分支網站上 IP-Pbx 或 PSTN 閘道的呼叫。 不過, 如果您要部署 SIP trunks, 則必須在每個幹線終止的網站上部署一個轉送伺服器。 在分支網站上的 IP PBX 或 PSTN 閘道呼叫中央網站路由的中繼伺服器不需要使用媒體旁路, 但建議使用媒體旁路。 這是因為, 如果您可以啟用媒體旁路, 它會減少媒體路徑延遲, 因此, 因為媒體路徑不需要追蹤信號路徑, 因此會改善媒體質量。 [媒體旁路] 也會減少池中的處理負載。
  
> [!NOTE]
> 媒體旁路無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。 Microsoft 已經測試了一組 PSTN 閘道, 並有已認證的合作夥伴, 且已使用 Cisco IP-Pbx 進行了一些測試。 只有在整合通訊開啟互通性計畫中列出的產品與版本, 才支援媒體旁路[, 請參閱探索已測試的裝置、基礎結構, 以及支援及擴充商務用 Skype 體驗的工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)。 
  
如果需要分支網站復原功能, Survivable 分支裝置或前端伺服器、中繼伺服器和閘道的組合必須部署在分支網站上。 (分支網站復原的假設是, 目前狀態與會議不會在網站上復原。)如需有關分支網站規劃語音的指導方針, 請參閱[商務用 Skype Server 中的企業語音復原方案](../enterprise-voice-solution/enterprise-voice-resiliency.md)。
  
針對 IP PBX 的互動, 如果 IP PBX 無法正確支援使用多個前期對話方塊與 RFC 3960 互動的早期媒體互動, 就可以將從 IP PBX 撥入通話的前幾個字剪切到 Lync 端點。 如果中央站台的中繼伺服器是路由在分支網站中斷的 IP PBX 路由呼叫, 這種行為可能會較嚴重, 因為需要更多的時間來完成通知。 如果您遇到這種情況, 請在分支網站上部署中繼伺服器, 這是減少前幾個字的剪輯的唯一方法。
  
最後, 如果您的中央網站有 TDM PBX, 或者您的 IP PBX 不會消除 PSTN 閘道的需求, 則您必須在連線轉送伺服器和 PBX 的呼叫路由中部署閘道。
  
> [!NOTE]
> 若要改善獨立轉送伺服器的媒體效能, 您應該在這些伺服器的網路介面卡上啟用接收端縮放 (RSS)。 RSS 可讓伺服器上的多個處理常式並行處理傳入的資料包。 如需詳細資訊, 請參閱「[Windows Server 中的接收端縮放增強功能](https://go.microsoft.com/fwlink/p/?LinkId=268731)」。 如需有關如何啟用 RSS 的詳細資訊, 請參閱您的網路介面卡檔。 
  

