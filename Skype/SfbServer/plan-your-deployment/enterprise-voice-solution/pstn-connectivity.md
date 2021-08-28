---
title: 商務用 Skype Server 中的 PSTN 連線元件
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 深入瞭解商務用 Skype Server 中企業語音的 SIP 主幹及 PSTN 閘道。
ms.openlocfilehash: 8aa3914eac1a716380b69971b0c576186dbfac17
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620969"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>商務用 Skype Server 中的 PSTN 連線元件
 
深入瞭解商務用 Skype Server 中企業語音的 SIP 主幹及 PSTN 閘道。
  
企業等級的 VoIP 解決方案必須提供與公用交換電話網路 (PSTN) 之間的往來通話，且不犧牲任何服務品質 (QoS)。此外，使用者在撥號及接聽電話時應該不會意識到此基礎技術的存在。就使用者的觀點而言，Enterprise Voice 基礎結構與 PSTN 之間的通話應該就像是另一個 SIP 工作階段。
  
針對 PSTN 連線，您可以使用 PBX （也稱為直接 SIP 連結）或沒有 PBX) 部署 SIP 主幹或 PSTN 閘道 (。
  
## <a name="sip-trunking"></a>SIP 主幹

若不使用 PSTN 閘道，替代的方法是使用 SIP 主幹將企業語音解決方案連線至 PSTN。SIP 主幹可啟用下列案例：
  
- 公司防火牆內外的企業使用者可透過符合 E.164 格式號碼所指定，且以 PSTN (做為對應服務提供者之服務) 為電話終端，來撥打市內或長途電話。
    
- 任何 PSTN 訂閱者都可以透過撥打與企業使用者相關聯的直接向內撥號 (DID) 號碼，與位於公司防火牆內外的企業使用者連絡。
    
使用這個部署解決方案必須有 SIP 主幹服務提供者。 
  
## <a name="pstn-gateways"></a>PSTN 閘道

PSTN 閘道是協力廠商裝置，可轉譯企業語音基礎結構與 PSTN 或 PBX 之間的訊號和媒體。 PSTN 閘道與中繼伺服器搭配運作，以向企業語音用戶端呈現 PSTN 或 PBX 通話。 中繼伺服器也會向 PSTN 閘道呈現來自企業語音用戶端的通話，以路由傳送至 PSTN 或 PBX。 如需與 microsoft 合作以提供與商務用 Skype Server 搭配運作之裝置的合作夥伴清單，請參閱[Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。 
  
## <a name="private-branch-exchanges"></a>專用交換機

 如果您現有的語音基礎結構使用專用交換機 (PBX) ，您可以搭配企業語音使用 PBX。
  
支援的企業語音 PBX 整合案例如下：
  
- 支援媒體旁路且含有中繼伺服器的 IP-PBX。
    
- 需要獨立 PSTN 閘道的 IP-PBX。
    
- 含有獨立 PSTN 閘道的分時多工 (TDM) PBX。
    
> [!NOTE]
> 媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。 Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。 只有在 [整合通訊開啟互通性計畫-Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)所列的產品及版本支援媒體旁路。 
  
如需提供企業語音解決方案之合作夥伴的詳細資訊，請參閱[Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
  
如需提供企業語音硬體解決方案（包括 PSTN 閘道）之合作夥伴的詳細資訊，請參閱[Microsoft 整合通訊合作夥伴網站](https://go.microsoft.com/fwlink/p/?linkId=202836)。
