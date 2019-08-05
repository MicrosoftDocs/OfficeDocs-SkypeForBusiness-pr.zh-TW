---
title: 在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: '摘要: 瞭解如何在商務用 Skype Server 的 [拓撲產生器] 中定義 PSTN 閘道。'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190405"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>在商務用 Skype Server 的 [拓撲 Builder] 中定義閘道
 
**摘要:** 瞭解如何在商務用 Skype Server 的 [拓撲建立器] 中定義 PSTN 閘道。
  
請依照下列步驟使用拓撲 Builder 來定義對等, 您可以將該對等與中繼伺服器建立關聯, 以便為啟用企業語音的使用者提供公用的交換電話網絡 (PSTN) 連線。 對轉送伺服器的對等可以是 PSTN 閘道、IP PBX 或會話邊界控制器 (ITSP), 您可以透過設定 SIP 幹線來連線該服務提供者。
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>若要為中繼伺服器定義對等

1. 啟動拓撲產生器: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype server 2015**], 然後按一下 [**商務用 skype server 2015Topology**建立器]。
    
2. 在商務用 Skype Server、您的網站名稱、共用元件中, 以滑鼠右鍵按一下**PSTN 閘道**節點, 然後按一下 [**新 pstn 閘道**]。
3. 在 [**定義新的 IP/PSTN 閘道**] 中, 輸入對等的完整功能變數名稱 (FQDN) 或 IP 位址, 然後按 **[下一步]**。
    
    > [!NOTE]
    > 如果您將傳輸層安全性 (TLS) 指定為傳輸類型, 您必須指定 FQDN, 而不是對轉送伺服器對等的 IP 位址。 
  
4. 定義新 PSTN 閘道之 IP 位址的偵聽模式 (IPv4 或 IPv6), 然後按 **[下一步]**。

5. 為 PSTN 閘道定義根幹線。 幹線是由元組唯一識別的中繼伺服器與閘道之間的邏輯連線。
    
    {轉送伺服器 FQDN, 中繼伺服器偵聽埠 (TLS 或 TCP): 閘道 IP 和 FQDN, 閘道偵聽埠}
    
     - 在拓撲建立器中定義 PSTN 閘道時, 您必須定義根幹線, 才能成功將 PSTN 閘道新增到您的拓撲。
    
     - 移除關聯的 PSTN 閘道之後, 才能移除根主幹。
    
6. 在 [ **IP/PSTN 閘道偵聽埠**] 底下, 輸入閘道、PBX 或 SBC 將用來處理來自中繼伺服器的 SIP 訊息的偵聽埠, 該埠會與 PSTN 閘道的根幹線產生關聯。 (根據預設, 埠在 PSTN 閘道、PBX 或 SBC 上的傳輸控制通訊協定 (TCP) 和 5067 (針對傳輸層安全性 (TLS)) 都是5066。 在分支網站的 Survivable 分支裝置上, 預設埠為 5081 (適用于 TCP, 而5082則為 TLS)。)
    
7. 在 [ **SIP 傳輸通訊協定**] 底下, 按一下對等所使用的傳輸類型, 然後按一下 **[確定]**。
    
    > [!NOTE]
    > 出於安全性考慮, 我們強烈建議您將對等部署到可使用 TLS 的中繼伺服器。 
  
8. 在 [**關聯的中繼伺服器**] 底下, 選取 [中繼伺服器] 池以與此 PSTN 閘道的根幹線建立關聯。
    
9. 在 [**關聯的中繼伺服器埠**] 底下, 輸入中繼伺服器將用於來自閘道的 SIP 訊息的偵聽埠。
    
    > [!NOTE]
    > 在商務用 Skype Server 中有多個幹線支援, 您可以在中繼伺服器上定義多個 SIP 信號埠, 以便與多個 PSTN 閘道進行通訊。 在定義主幹時,**關聯的中繼伺服器埠**必須位於中繼伺服器所允許之各個通訊協定的偵聽埠範圍內。 此埠範圍是在商務用 Skype Server 和轉送池所定義。 以滑鼠右鍵按一下感興趣的中繼伺服器池, 然後選取 [**編輯屬性**]。 在 [**偵聽埠**] 欄位中指定埠範圍。
  
10. 請確定您定義的對等是執行中, 並使用您所指定的 FQDN 或 IP 位址。 然後按一下 **[完成]**。
    
11. 以滑鼠右鍵按一下**商務用 Skype Server**節點, 然後按一下 [**發佈拓撲**]。
    

