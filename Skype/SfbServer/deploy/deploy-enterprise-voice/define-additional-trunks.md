---
title: 在商務用 Skype Server 的 [拓撲產生器] 中定義其他 trunks
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲產生器] 中定義其他主幹與 [閘道對等]。'
ms.openlocfilehash: eeaddf6b5b150298e7a77b819464b3c0ef653b70
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245860"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 的 [拓撲產生器] 中定義其他 trunks
 
**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中, 定義在中繼伺服器與閘道對等之間的其他主幹。
  
請依照下列步驟來定義您可以將對等與中繼伺服器產生關聯的其他主幹。 對等可為使用者提供可連線至公用交換電話網絡 (PSTN) 的企業語音功能。 對等可以是 PSTN 閘道、IP PBX, 或網際網路電話服務提供者 (ITSP) 的會話邊界控制器 (SBC)。
  
主幹是中繼伺服器與閘道之間的邏輯連線。
  
> [!NOTE]
> 本主題假設您已使用至少一個 collocated 或獨立的中繼伺服器或池來設定 PSTN 閘道和根幹線, 如所述, 請參閱在部署檔中的商務用 Skype Server 中的 [拓撲建立器] 中的 [[定義閘道](define-a-gateway.md)]。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中繼伺服器與閘道對等之間定義額外主幹

1. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。
    
2. 在商務用 Skype Server、您的網站名稱、**共用元件**中, 以滑鼠右鍵按一下 [ **Trunks** ] 節點, 然後按一下 [**新幹線**]。
   1. 在 [**定義新主幹**] 中, 指定要唯一識別主幹的易記名稱。 您不能有兩個名稱相同的 trunks。
    
      > [!NOTE]
      > 如果您將傳輸層安全性 (TLS) 指定為傳輸類型, 您必須指定 FQDN, 而不是對轉送伺服器對等的 IP 位址。 
  
3. 在 [**關聯的 PSTN 閘道**] 底下, 選取 PSTN 閘道對, 以與此幹線建立關聯。
    5. 在 [ **PSTN 閘道的偵聽埠**] 底下, 輸入對等 (PSTN 閘道、IP PBX 或 SBC) 的偵聽埠, 將會從要與此幹線關聯的中繼伺服器接收 SIP 訊息。 預設對等埠是針對傳輸控制通訊協定 (TCP) 和 5067 (針對傳輸層安全性 (TLS)) 的5066。 預設的 Survivable 分支裝置埠是適用于 TCP 的 5081, 以及適用于 TLS 的5082。
    
4. 在 [ **SIP 傳輸通訊協定**] 底下, 按一下對等所使用的傳輸類型。
    
    > [!NOTE]
    > 出於安全性考慮, 我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。 
  
5. 在 [**關聯的中繼伺服器**] 底下, 選取 [轉送伺服器] 池以與此對等方的根幹線建立關聯
    
6. 在 [**關聯的中繼伺服器埠**] 底下, 輸入中繼伺服器將從對等接收 SIP 訊息的偵聽埠。
    
    > [!NOTE]
    > 在商務用 Skype Server 中有多個幹線支援, 不能使用相同的**關聯中繼伺服器埠**和**偵聽埠 (適用于 IP/PSTN 閘道**) 來設定不同主幹名稱的兩個 trunks
  
    > [!NOTE]
    > 在商務用 Skype Server 中有多個幹線支援, 您可以在中繼伺服器上定義多個 SIP 信號埠, 以便與多個對等進行通訊。 在定義主幹時,**關聯的中繼伺服器埠**編號必須在中繼伺服器所允許之個別通訊協定的偵聽埠範圍內。 此埠範圍是在商務用 Skype Server 和中繼伺服器池底下定義。 以滑鼠右鍵按一下相關的中繼伺服器池, 然後選取 [**編輯屬性**]。 在 [**偵聽埠**] 欄位中指定埠範圍。
  
7. 按一下 [確定]****。 
    

