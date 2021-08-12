---
title: 在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 規劃使用 sip 主幹提供者的 E9-1-1 部署的 SIP 主幹拓撲，商務用 Skype Server 企業語音中。
ms.openlocfilehash: 5e669f8fc3149ac362e265a8e850e145f95c72567be99946fe0e37c0faa82130
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283055"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
 
規劃使用 sip 主幹提供者的 E9-1-1 部署的 SIP 主幹拓撲，商務用 Skype Server 企業語音中。
  
商務用 Skype Server 使用 SIP 主幹將緊急通話連接至 E9-1-1 服務提供者。 您可以在一個中央網台、多個中央網台或每個分支網站上設定 E9-1-1 的緊急服務 SIP 主幹。 不過，如果來電者的網站與主控緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則使用者的語音原則中將需要特殊的電話使用方式記錄，以便透過本機公用交換電話網路 (PSTN) 閘道將通話路由傳送至 ECRC。 如果通話許可控制並行通話限制有效，則有同樣的需求。
  
在商務用 Skype Server 環境中執行 SIP 主幹的方式有兩種：
  
- 使用多宿主的轉送伺服器，利用其向外公開路由的介面與 SIP 主幹提供者通訊。
    
- 使用內部部署會話邊界控制器 (SBC) ，以在轉送伺服器和 SIP 主幹提供者的服務之間提供安全的分割點。
    
如果您選擇後者，請確定您所選擇的 SBC 品牌與型號已取得認證，並且支援傳遞「目前狀態資訊資料格式位置物件」(PIDF-LO) 位置資料做為其 SIP INVITE 的一部分。 否則電話將會送達去除其位置資訊的緊急服務服務提供者。 如需認證 SBCs 的詳細資訊，請參閱「 [Microsoft Lync 的基礎結構合格](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)」和「[商務用 Skype 的電話語音基礎結構](../../../SfbPartnerCertification/certification/infra-gateways.md)」。 
  
E9-1-1 服務提供者為您提供一組 SBC 的存取做為後備之用。 您需要對轉送伺服器拓撲及通話路由設定進行幾項決策。 您是要將兩台 SBC 視為對等，並對它們之間的通話使用循環配置資源路由；或是要將一個 SBC 指派為主要，而另一個指派為次要呢？
  
如需在商務用 Skype Server 中部署 sip 主幹的詳細資訊，請參閱[商務用 Skype Server 中的 sip trunk](sip-trunking.md)。 為了協助決定如何部署 E9-1-1 的 SIP 主幹，您應該先回答下列問題。
  
 **您應該在專用的租用網際網路連線上還是共用的網際網路連線上部署 SIP 主幹？**
  
> 重點是一定要能夠接通緊急通話。專用線路可提供不被網路上其他流量佔用的連線，並讓您能夠實作服務品質 (QoS)。請記住，如果您透過公用網際網路連線至緊急服務服務提供者，而且需要保證緊急電話的機密性，則需要 IPSec 加密。 
    
 **您的 E9-1-1 部署是針對嚴重損壞而設計嗎？**
  
> 因為這是緊急解決方案，所以恢復能力很重要。 在災難容錯位置部署主要和次要轉送伺服器和 SIP 主幹。 最好是部署最接近其支援之使用者的主要轉送伺服器，並將容錯移轉呼叫路由傳送至位於不同地理位置) 中的次要轉送伺服器 (。 
    
 **您是否應該為每個分公司部署個別的 SIP 主幹？**
  
> 商務用 Skype Server 提供數個策略，用以處理分支辦公室中的語音恢復作業，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將呼叫推出至本機閘道。 如需詳細資訊，請參閱[商務用 Skype Server 中的 SIP](sip-trunking.md)主幹。
    
 **是否啟用通話許可控制 (CAC)?**
  
> 商務用 Skype Server 不會處理緊急通話，其方式不是一般呼叫。 因此，頻寬管理或通話許可控制 (CAC) 可能對 E9-1-1 組態有負面影響。 如果啟用 CAC，且在路由緊急通話的連結上的流量超出設定的限制，則緊急通話可能會被封鎖或路由至本機 PSTN 閘道。 如同本主題稍早所述，這類通話將會沒有位置資料，並且必須以手動方式路由至 ECRC。
