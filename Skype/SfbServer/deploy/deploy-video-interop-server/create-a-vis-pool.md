---
title: 在商務用 Skype Server 中建立 VIS 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 摘要：使用拓撲產生器在商務用 Skype 伺服器中建立視頻互通性伺服器池。
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798050"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a>在商務用 Skype Server 中建立 VIS 池
 
**摘要：** 在商務用 Skype Server 中使用 [拓撲建立器] 建立視頻互通性伺服器池。
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a>使用拓撲產生器建立 VIS 或 VIS 池

1. 在前端伺服器上開啟拓撲建立器。 從 [拓撲建立器] 的左窗格中，以滑鼠右鍵按一下 [**影片互通性伺服器池**]，然後選擇 [**新增視頻互通性伺服器** 
    
2. 這將會開啟 [**建立新的視頻互通性伺服器池**] 嚮導。 為新的視頻交互操作伺服器提供 [池 FQDN]，然後選取 [**此池擁有一個伺服器**] 或 [**此池中有多個伺服器**（根據您的需求）]，然後按 **[下一步]**。
    
    如果您想要部署視頻互通性伺服器池來提供高可用性，請選取 [**此池子擁有多個伺服器**]。 請記住，這個選項如下： 
    
    - 您必須部署 DNS 負載平衡，以支援視頻互通性伺服器池。 
    
   - 在下一頁的 [**定義此 pool 中的電腦**] 專案中，將池中每個伺服器的**電腦 FQDN**輸入至 [文字] 欄位，然後按一下 [**新增**]。 重複此步驟，將另一個影片交互操作伺服器新增至該資源庫。 在池中定義所有電腦之後，請按 **[下一步]**。
    
     如果您只想在池中部署一個視頻交互操作伺服器，因為您不需要高可用性，請選取 [**此池有一個伺服器**]，然後按 **[下一步]**。
    
3. 從下拉式清單中選取下一個躍點池子/FE，然後按 **[下一步]**。
    
4. 選取要與 VIS 建立關聯的邊緣池，然後按下 **[完成]**。
    
5. 設定 TCP 或 TLS 埠。
    
    從 [拓撲建立器] 的左窗格選取 [新增的視頻互通性伺服器]，以滑鼠右鍵按一下它，然後選擇 [**編輯屬性**]。 根據您的需求啟用或更新 TCP 或 TLS 埠，然後選擇 **[確定]**。 雖然已新增預設的 TLS，但只有 TCP 經過 Cisco 整合通訊管理員（CallManager 或 CUCM）才能完全測試。
    
6. 新增視頻閘道。 若要這樣做，請展開 [共用元件]，以滑鼠右鍵按一下 [**視頻閘道**]，然後選取 [**新增視頻**
    
7. 提供 [視頻閘道 FQDN] 或 [IP 位址]。 [視頻閘道] 可能位於子域或其他網域中。 您系統的 VTCs 所使用的 CUCM 會做為視頻閘道。
    
8. 視需要選取 [IPv4] 或 [IPv6]。 您可以使用所有設定的 IP 位址，或將服務使用限制在選取的 IP 位址。
    
9. 選取視頻閘道的偵聽埠。 選取傳輸通訊協定（TCP 或 TLS），並將它與針對視頻 SIP 幹線設定的視頻互通性伺服器建立關聯。 視頻閘道的傳輸通訊協定應該與為 VIS 設定的傳輸通訊協定相符。
    
10. 在上述步驟完成之後，就會新增對應的 SIP 視頻幹線。 以滑鼠右鍵按一下 SIP 影片幹線，然後選取剛剛新增的主幹。 影片的主幹名稱、相關聯的視頻互通性伺服器、SIP 傳輸通訊協定和埠都可以全部變更。 
    
    > [!NOTE]
    >  影片交互操作伺服器支援1： N trunks。 因此，您可以新增多個 trunks，與單一的視頻交互操作伺服器產生關聯，而每個幹線則會在不同的視頻閘道上結束。 限制是某個特定的視頻閘道有一個且只有一個主幹，可以定義到商務用 Skype Server 部署。
  
11. 如在[商務用 Skype Server 2015 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md)中所述，發佈拓撲檔。
    
    > [!NOTE]
    > 若要改善復原能力，您可能會想要設定第二個視頻互通性伺服器或 VIS 池，或備份前端池。 如需詳細資訊，請參閱[復原機制](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
使用拓撲產生器執行的所有工作現在都應該已完成。 繼續在新的 VIS 伺服器或伺服器上安裝軟體。
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中部署 VIS 伺服器角色](deploy-the-vis-server-role.md)

[在商務用 Skype Server 中規劃影片互通性伺服器](../../plan-your-deployment/video-interop-server.md)
  
[在商務用 Skype Server 2015 中建立和發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md)
