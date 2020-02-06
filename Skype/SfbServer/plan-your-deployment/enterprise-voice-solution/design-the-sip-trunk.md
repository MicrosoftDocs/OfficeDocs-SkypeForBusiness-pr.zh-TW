---
title: 在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 針對使用 SIP 中繼提供者的 E9-1 1 部署，在商務用 Skype Server Enterprise Voice 中規劃 SIP 中繼拓撲。
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803073"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>在商務用 Skype Server 中設計 E9-1-1 的 SIP 主幹
 
針對使用 SIP 中繼提供者的 E9-1 1 部署，在商務用 Skype Server Enterprise Voice 中規劃 SIP 中繼拓撲。
  
商務用 Skype 伺服器使用 SIP trunks，將緊急呼叫連線至 E9-1-1 服務提供者。 您可以在一個中央網站、多個中央網站或每個分支網站上設定 E9-1-1 的緊急服務 SIP trunks。 不過，如果呼叫者的網站與託管緊急服務 SIP 主幹的網站之間的 WAN 連結無法使用，則在斷開連接的網站上由使用者所撥的通話將需要使用者語音原則中的特殊電話使用記錄，將呼叫路由至ECRC 透過本機的公用交換電話網絡（PSTN）閘道。 如果通話許可控制併發通話限制生效，就是如此。
  
在商務用 Skype Server 環境中，有兩種方式可以實施 SIP 主幹：
  
- 使用多宿主的出局轉送伺服器，使用其向外公開路由介面與 SIP 中繼提供者通訊。
    
- 使用內部部署會話邊界控制器（SBC），在中繼伺服器與 SIP 中繼提供者的服務之間提供安全的 demarcation 點。
    
如果您選擇後一個方法，請確定您所選擇的 SBC 與模型已獲認證，並且支援將目前狀態資訊資料格式位置物件（PIDF-LO）位置資料傳送成其 SIP 邀請的一部分。 否則，來電將會在緊急服務服務提供者去除其位置資訊時收到。 如需有關驗證的 SBCs 的詳細資料，請參閱「適用[于 Microsoft Lync 的基礎結構合格](https://go.microsoft.com/fwlink/p/?LinkId=248425)」和「[商務用 Skype 的電話架構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)」。 
  
E9-1-1 服務提供者會提供一組半形的存取權，以實現冗余。 您需要針對中繼伺服器拓撲和呼叫路由設定進行數個決策。 您會將 SBCs 視為同等對等，並使用迴圈式路由來進行呼叫，或是將一個 SBC 指派為主要的，另一個是副？
  
如需在商務用 Skype Server 中部署 SIP 幹線的詳細資料，請參閱[商務用 Skype 伺服器中的 sip 中繼](sip-trunking.md)。 下列問題將協助您決定如何部署 E9 的 SIP trunks-1-1。
  
 **您是否應該透過專用租使用者或共用的網際網路連線來部署 SIP 幹線？**
  
> 緊急通話永遠都是重要的。 專用線路提供的連線功能不會被網路上的其他流量搶佔，並可讓您實現服務品質（QoS）。 請記住，如果您是透過公用網際網路連線到緊急服務服務提供者，而且您需要保證緊急通話的機密性，則需要進行 IPSec 加密。 
    
 **您的 E9-1-1 部署是否專為災難耐受性而設計？**
  
> 因為這是緊急解決方案，所以復原非常重要。 在災難容錯位置部署主要和次要轉送伺服器和 SIP trunks。 建議您部署最接近支援的使用者的主要轉送伺服器，並透過次要轉送伺服器（位於不同的地理位置）路由容錯移轉呼叫。 
    
 **您是否應該針對每個分支機搆部署個別的 SIP 幹線？**
  
> 商務用 Skype 伺服器提供幾項策略，可處理分支辦公室中的語音復原，包括：擁有彈性資料網路、在每個分支部署 SIP 幹線，或在中斷期間將呼叫推送到本機閘道。 如需詳細資訊，請參閱[商務用 Skype 伺服器中的 SIP 中繼](sip-trunking.md)。
    
 **已啟用呼叫許可控制（CAC）嗎？**
  
> 商務用 Skype 伺服器不會處理緊急呼叫（與一般通話不同）。 基於這個原因，頻寬管理或呼叫許可控制（CAC）會對 E9-1-1 設定造成負面影響。 如果啟用了 CAC，緊急通話會遭到封鎖，或路由到本機 PSTN 閘道，且在路由緊急通話的連結上超過設定的限制。 如本主題前面所示，此類呼叫將沒有位置資料，必須手動路由至 ECRC。
    

