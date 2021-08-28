---
title: 商務用 Skype Server 中轉送伺服器的部署指導方針
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 本主題說明轉送伺服器部署的規劃指導方針。
ms.openlocfilehash: a524d478797c534950637d10efc39e0827d2f2a4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629535"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>商務用 Skype Server 中轉送伺服器的部署指導方針
 
本主題說明轉送伺服器部署的規劃指導方針。
  
## <a name="collocated-or-stand-alone-mediation-server"></a>組合或獨立轉送伺服器？

「轉送伺服器」預設會在中央網站的前端集區中的 Standard Edition 伺服器或前端伺服器上組合。 可以處理之公用交換電話網路 (PSTN) 通話的數目，以及集區中所需的機器數目會取決於下列專案：
  
- 轉送伺服器集區所控制的閘道對等數目。
    
- 透過這些閘道的高磁片流量週期。
    
- 媒體略過轉送伺服器之來電所占的百分比。
    
當您進行規劃時，請務必考慮 PSTN 通話的媒體處理需求，以及不支援媒體旁路的 A/V 會議，以及處理需要支援之繁忙小時通話數目之信號互動的處理方式。 如果您沒有足夠的 CPU，您必須部署一部獨立的轉送伺服器集區。 此外，PSTN 閘道、IP PBXs 和 SBCs 必須分割為由一個集區中的組合轉送伺服器，以及一或多個獨立集區中的獨立轉送伺服器所控制的子集。
  
如果您已部署 PSTN 閘道、IP PBXs 或會話邊界控制器 (SBCs) 與轉送伺服器集區互動，則必須與包含單一轉送伺服器集區的獨立集區相關聯。 您的 PSTN 閘道、IP-PBXs 或 SBCs 需要做的部分事情包括：
  
- 在集區中執行網路層網域名稱系統 (DNS) 負載平衡 (或將流量統一傳送至集區中的所有轉送伺服器) 。
    
- 接受來自集區中任何轉送伺服器的流量。
    
您可以使用商務用 Skype 規劃工具評估組合您的前端集區的轉送伺服器是否可以處理該負載。 如果您的環境無法符合這些需求，則您必須部署獨立的轉送伺服器集區。
  
## <a name="central-site-and-branch-site-considerations"></a>中央網站與分支網站的考量事項

 中央網站上的中繼伺服器可用來路由分支網站上 IP-PBX 或 PSTN 閘道的電話。 不過，如果您部署 SIP 主幹，您必須在每個主幹終止的網站上部署轉送伺服器。 在分支網站上的 IP-PBX 或 PSTN 閘道的中央網站路由呼叫轉送伺服器，不需要使用媒體旁路，但建議使用媒體旁路。 這是因為，如果您可以啟用媒體旁路，它會縮短媒體路徑延遲時間，因此，由於沒有必要使用媒體路徑來追蹤信號路徑，因此會改善媒體質量。 媒體旁路也可減少集區上的處理負載。
  
> [!NOTE]
> 媒體旁路不會與每個 PSTN 閘道、IP-PBX 及 SBC 互動。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 媒體旁路只支援整合通訊開啟互通性計畫中所列的產品和版本。在[探索已測試的裝置、基礎結構，以及支援和擴充您的商務用 Skype 經驗的工具](http://partnersolutions.skypeforbusiness.com/solutionscatalog)時，會支援 Lync Server。 
  
如果需要分支網站恢復功能，則必須在分支網站上部署 Survivable 分支裝置或前端伺服器、轉送伺服器和閘道的組合。  (以分支網站恢復的設想，其目前狀態和會議不會在網站上恢復。 ) 如需有關如何進行語音規劃的分支網站的指導，請參閱[Plan for 企業語音韌性 in 商務用 Skype Server](../enterprise-voice-solution/enterprise-voice-resiliency.md)。
  
在與 IP-PBX 互動的情況下，如果 IP-PBX 無法正確支援與多個早期對話方塊和 RFC 3960 互動的早期媒體互動，則可以從 IP-PBX 至 Lync 端點的來電中，將問候語的前幾個字裁剪。 如果中央網站上的中繼伺服器是為其整條路由是終止於分支網站的 IP-PBX 來路由電話，前述行為可能會更嚴重，因為需要更多時間來完成訊號。 如果您遇到此行為，請在分支網站上部署轉送伺服器，以減少前幾個字的裁剪。
  
最後，如果您的中央網站上有 TDM PBX，或是您的 IP-PBX 非得使用 PSTN 閘道不可，則您必須在連接中繼伺服器與 PBX 的電話路由上部署閘道。
  
> [!NOTE]
> 若要改善獨立轉送伺服器的媒體效能，您應該在這些伺服器的網路介面卡上啟用接收端伸縮 (RSS) 。 RSS 可讓伺服器上的多個處理器同時處理內送的封包。 如需詳細資訊，請參閱「[Windows Server 中的接收端擴充功能增強功能](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11))」。 如需如何啟用 RSS 的詳細資訊，請參閱您的網路介面卡檔。 
