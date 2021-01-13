---
title: 在商務用 Skype Server 的拓撲產生器中定義閘道
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要：瞭解如何在商務用 Skype Server 的拓撲產生器中定義 PSTN 閘道。
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837023"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 的拓撲產生器中定義閘道
 
**摘要：** 瞭解如何在商務用 Skype Server 的拓撲產生器中定義 PSTN 閘道。
  
請遵循下列步驟，使用拓撲產生器來定義與轉送伺服器相關聯的對等對等能力，以便為已啟用 Enterprise Voice 的使用者提供公用交換電話網路 (PSTN) 連線。 對等與轉送伺服器的對等可以是 Internet 電話語音服務提供者 (SBC) 的 PSTN 閘道、IP-PBX 或會話邊界控制器， (透過設定 SIP 主幹來連接的 ITSP) 。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>若要定義轉送伺服器的對等

1. 啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype server 2015**]，然後按一下 [ **商務用 skype server 2015Topology** 建立器]。
    
2. 在 [商務用 Skype 伺服器] 底下，您的網站名稱，共用元件，以滑鼠右鍵按一下 [ **PSTN 閘道** ] 節點，然後按一下 [ **新增 pstn 閘道**]。
3. 在 **[定義新的 IP/PSTN 閘道]** 中，輸入對等的完整網域名稱 (FQDN) 或 IP 位址，然後按一下 **[下一步]**。
    
    > [!NOTE]
    > 如果您指定傳輸層安全性 (TLS) 做為傳輸類型，您必須指定 FQDN 而非轉送伺服器對等的 IP 位址。 
  
4. 定義您新的 PSTN 閘道的 IP 位址的聆聽模式 (IPv4 或 IPv6)，然後按一下 **[下一步]**。

5. 定義 PSTN 閘道的根主幹。 主幹是由元組唯一識別的轉送伺服器與閘道之間的邏輯連接。
    
    {轉送伺服器 FQDN、轉送伺服器接聽埠 (TLS 或 TCP) ：閘道 IP 和 FQDN，閘道聆聽埠}
    
     - 在拓撲產生器中定義 PSTN 閘道時，您必須定義一個根主幹，以順利將 PSTN 閘道新增至您的拓撲。
    
     - 必須先移除關聯的 PSTN 閘道，才能移除根主幹。
    
6. 在 [ **IP/PSTN 閘道的聆聽埠**] 底下，輸入閘道、PBX 或 SBC 將用於從轉送伺服器將其與 PSTN 閘道根主幹相關聯的 SIP 郵件所使用的收聽埠。  (依預設，在 PSTN 閘道、PBX 或 SBC 上，傳輸控制通訊協定 (TCP) 和5067的傳輸層安全性 (TLS) 的埠是5066。 在分支網站上的 Survivable 分支裝置中，TCP 和5082的預設埠為5081，以供 TLS 使用。 ) 
    
7. 在 **[SIP 傳輸通訊協定]** 下，按一下對等使用的傳輸類型，然後按一下 **[確定]**。
    
    > [!NOTE]
    > 基於安全性考慮，強烈建議您將對等部署至可使用 TLS 的轉送伺服器。 
  
8. 在 [關聯的轉送伺服器] 底下，選取要與此 PSTN 閘道 **之** 根主幹產生關聯的轉送伺服器集區。
    
9. 在 [關聯的中繼 **伺服器埠**] 底下，輸入轉送伺服器將用於來自閘道的 SIP 訊息的聆聽埠。
    
    > [!NOTE]
    > 在商務用 Skype Server 中使用多個主幹支援，您可以在轉送伺服器上定義多個 SIP 信號埠，以與多個 PSTN 閘道進行通訊。 在定義主幹時，關聯的中繼 **伺服器埠** 必須位於轉送伺服器所允許之個別通訊埠的偵聽埠範圍內。 此埠範圍是在商務用 Skype Server 和中繼集區所定義。 在感興趣的轉送伺服器集區上按一下滑鼠右鍵，然後選取 [ **編輯屬性**]。 在 **[聆聽連接埠]** 欄位中指定連接埠範圍。
  
10. 確定您定義的對等機器正在執行，並使用您指定的 FQDN 或 IP 位址。 然後按一下 **[完成]**。
    
11. 以滑鼠右鍵按一下 [ **商務用 Skype 伺服器** ] 節點，然後按一下 [ **發行拓撲**]。
    

