---
title: 在商務用 Skype Server 中定義拓撲產生器中的其他主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要：瞭解如何在商務用 Skype Server 的拓撲產生器中，定義轉送伺服器與閘道對等之間的其他主幹。
ms.openlocfilehash: 42f435079a66f7dba6c325ad8afbb1b28a3e3753
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585853"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 中定義拓撲產生器中的其他主幹
 
**摘要：** 瞭解如何在商務用 Skype Server 的拓撲產生器中，定義轉送伺服器與閘道對等之間的其他主幹。
  
請遵循下列步驟來定義您可以將對等與轉送伺服器產生關聯的其他主幹。 對等使用者可為企業語音啟用公用交換電話網路 (PSTN) 的連線。 對等可以是 Internet 電話語音服務提供者的 PSTN 閘道、IP-PBX 或會話邊界控制器 (SBC)  (ITSP) 。
  
主幹是轉送伺服器與閘道之間的邏輯連接。
  
> [!NOTE]
> 本主題假設您已設定 PSTN 閘道和具有至少一個組合或獨立轉送伺服器或集區的根主幹，如在部署檔中的[商務用 Skype Server 中定義拓撲產生器中的閘道](define-a-gateway.md)所述。
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在轉送伺服器與閘道對等間定義其他主幹

1. 啟動拓撲產生器：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server 2015**]，然後按一下 [**商務用 Skype Server 2015Topology** 產生器]。
    
2. 在 [商務用 Skype Server] 底下，您的網站名稱，**共用元件**，以滑鼠右鍵按一下 **主幹** 節點，然後按一下 [**新增主幹**]。
   1. 在 [ **定義新的主幹**] 中，指定可唯一識別主幹的易記名稱。 您不能有兩個具有相同名稱的主幹。
    
      > [!NOTE]
      > 如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。 
  
3. 在 [ **關聯的 pstn 閘道**] 底下，選取 PSTN 閘道對等相關聯的主幹。
    5. 在 [ **適用于 PSTN 閘道的聆聽埠**] 底下，輸入對等 (PSTN 閘道、IP-PBX 或 SBC) 將要從轉送伺服器接收 SIP 郵件的收聽埠，該伺服器將會與此主幹產生關聯。 傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的預設對等埠為5066。 Survivable 的預設分支裝置埠是5081的 TCP 和5082的 TLS。
    
4. 在 [ **SIP 傳輸通訊協定**] 下，按一下對等使用的傳輸類型。
    
    > [!NOTE]
    > 基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。 
  
5. 在 [關聯的中繼 **伺服器**] 底下，選取要與此對等的根主幹相關聯的轉送伺服器集區。
    
6. 在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器接收來自對等的 SIP 訊息的聆聽埠。
    
    > [!NOTE]
    > 在商務用 Skype Server 中有多個主幹支援時，不能使用 IP/PSTN 閘道的相同 **關聯轉送伺服器埠** 和 **偵聽埠來** 設定具有不同主幹名稱的兩個主幹
  
    > [!NOTE]
    > 在商務用 Skype Server 中使用多個主幹支援，可在轉送伺服器上定義多個 SIP 信號埠，以與多個對等機進行通訊。 在定義主幹時，關聯的中繼 **伺服器埠** 號碼必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。 此埠範圍是在商務用 Skype Server 和轉送伺服器集區下定義。 在相關的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。 在 **[聆聽連接埠]** 欄位中指定連接埠範圍。
  
7. 按一下 [確定]。 
    

