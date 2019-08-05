---
title: 商務用 Skype Server 的加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商務用 Skype 伺服器使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或交叉對內部網路周邊, 所有伺服器對伺服器的流量都必須是 MTLS。 將商務用 Skype Server 連線至協力廠商 IPPBX 系統或 SIP trunks TLS 是選擇性的, 但強烈建議在中繼伺服器與媒體閘道之間進行。 如果在此連結上設定 TLS, 則需要 MTLS。 因此, 閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192945"
---
# <a name="encryption-for-skype-for-business-server"></a>商務用 Skype Server 的加密
 
商務用 Skype 伺服器使用 TLS 和 MTLS 來加密立即訊息。 不論流量是限制在內部網路或交叉對內部網路周邊, 所有伺服器對伺服器的流量都必須是 MTLS。 將商務用 Skype Server 連線至協力廠商 IPPBX 系統或 SIP trunks TLS 是選擇性的, 但強烈建議在中繼伺服器與媒體閘道之間進行。 如果在此連結上設定 TLS, 則需要 MTLS。 因此, 閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。
  
> [!NOTE]
> 已在2014中發佈有關 SSL 3.0 的安全性通知。 在商務用 Skype Server 2015 中停用 SSL 3.0 是受支援的選項。 若要深入瞭解安全性建議, 請參閱[在 Lync server 2013 和商務用 Skype server 2015 中停用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。<br/>
**安全性注意事項:** 為了確保使用最強的加密通訊協定, 商務用 Skype Server 2015 將以下列順序向用戶端提供 TLS 加密通訊協定: **tls 1.2、tls 1.1、TLS 1.0**。 TLS 是商務用 Skype Server 2015 的一個重要層面, 因此需要維持支援的環境。<br/>
**安全性注意事項:** 為了確保使用最強的加密通訊協定, 商務用 Skype Server 2019 將以下列順序向用戶端提供 TLS 加密通訊協定: **tls 1.3、tls 1.2**。 TLS 是商務用 Skype Server 2019 的一個重要層面, 因此需要維持支援的環境。 
  
下表摘要列出每種通信量類型的通訊協定需求。 
  
**交通防護**

|**流量類型**|**受**|
|:-----|:-----|
|伺服器與伺服器  <br/> |MTLS  <br/> |
|用戶端到伺服器  <br/> |EAP-TLS  <br/> |
|立即訊息和目前狀態  <br/> |EAP-TLS  <br/> |
|媒體的音訊和影片與桌面共用  <br/> |SRTP  <br/> |
|桌面共用 (信號)  <br/> |EAP-TLS  <br/> |
|網路會議  <br/> |EAP-TLS  <br/> |
|會議內容下載、通訊錄下載、通訊群組延伸  <br/> |IP-HTTPS  <br/> |
   
## <a name="media-encryption"></a>媒體加密

媒體流量是使用安全的 RTP (SRTP) 來加密, 這是一種即時傳輸通訊協定 (RTP) 設定檔, 可為 RTP 流量提供保密性、驗證及重放攻擊保護。 此外, 在中繼伺服器與其內部下一個躍點之間的兩個方向上, 媒體也會使用 SRTP 來加密。 在中繼伺服器與媒體閘道之間的兩個方向上, 媒體的流動方式都有選擇性地加密及建議。 中繼伺服器可以支援對媒體閘道進行加密, 但閘道必須支援 MTLS 和儲存憑證。
  
> [!NOTE]
> 如需設定混合式混合式的詳細資訊, 請參閱[規劃混合式連線性](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。
  
## <a name="fips"></a>FIPS

商務用 Skype Server 和 Microsoft Exchange Server 2016 的運作方式支援聯邦資訊處理標準 (FIPS) 140-2 演算法 (如果 Windows 伺服器作業系統已設定為使用 FIPS 140-2 演算法進行系統加密). 若要實現 FIPS 支援, 您必須設定執行商務用 Skype Server 的每個伺服器以支援它。
  

