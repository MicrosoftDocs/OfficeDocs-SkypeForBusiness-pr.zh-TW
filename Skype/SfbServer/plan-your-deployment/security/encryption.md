---
title: 商務用 Skype Server 的加密
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商務用 Skype Server 會使用 TLS 及 MTLS 來加密立即訊息。 不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。 將商務用 Skype Server 連接至協力廠商 IPPBX 系統或 SIP 主幹 TLS 是選用的，但是強烈建議在轉送伺服器和媒體閘道之間進行。 如果在此連結上設定 TLS，則需要 MTLS。 因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。
ms.openlocfilehash: 3ee649f62e2855f959b2ee9fdc25bdb2d77fa6e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849716"
---
# <a name="encryption-for-skype-for-business-server"></a>商務用 Skype Server 的加密
 
商務用 Skype Server 會使用 TLS 及 MTLS 來加密立即訊息。 不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。 將商務用 Skype Server 連接至協力廠商 IPPBX 系統或 SIP 主幹 TLS 是選用的，但是強烈建議在轉送伺服器和媒體閘道之間進行。 如果在此連結上設定 TLS，則需要 MTLS。 因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。
  
> [!NOTE]
> 有關 SSL 3.0 的安全性通報已在2014中發佈。 在商務用 Skype Server 2015 中停用 SSL 3.0 是支援的選項。 若要深入瞭解安全性通報，請參閱[在 Lync Server 2013 中停用 SSL 3.0 及商務用 Skype Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)。<br/>
**安全性附注：** 為了確保使用最強的加密通訊協定，商務用 Skype Server 2015 會以下列順序為用戶端提供 tls 加密通訊協定： **tls 1.2，tls 1.1，tls 1.0**。 TLS 是商務用 Skype Server 2015 的重要層面，因此必須使用此功能才能維護支援的環境。<br/>
**安全性附注：** 為了確保使用最強的加密通訊協定，商務用 Skype Server 2019 會以下列順序為用戶端提供 tls 加密通訊協定： **tls 1.3，tls 1.2**。 TLS 是商務用 Skype Server 2019 的重要層面，因此必須使用此功能才能維護支援的環境。 
  
下表摘要說明每一種流量類型的通訊協定需求。 
  
**流量保護**

|**流量類型**|**提供保護的通訊協定**|
|:-----|:-----|
|伺服器對伺服器  <br/> |MTLS  <br/> |
|用戶端對伺服器  <br/> |TLS  <br/> |
|立即訊息和目前狀態  <br/> |TLS  <br/> |
|音訊和視訊及媒體的桌面共用  <br/> |SRTP  <br/> |
|桌面共用 (訊號)  <br/> |TLS  <br/> |
|Web 會議  <br/> |TLS  <br/> |
|會議內容下載、通訊錄下載、通訊群組擴充  <br/> |HTTPS:  <br/> |
   
## <a name="media-encryption"></a>媒體加密

媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。 此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。 轉送伺服器和媒體閘道之間的兩種方向的媒體都是可選擇性地加密及建議的。 中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。
  
> [!NOTE]
> 如需設定混合式的詳細資訊，請參閱 [規劃混合](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)式連線。
  
## <a name="fips"></a>FIPS

商務用 Skype Server 和 Microsoft Exchange Server 2016 的運作方式，支援聯邦資訊處理標準 (FIPS) 140-2 演算法（如果 Windows 伺服器作業系統設定為使用 FIPS 140-2 演算法進行系統加密）。 若要實施 FIPS 支援，您必須設定每台執行商務用 Skype Server 的伺服器以支援它。
