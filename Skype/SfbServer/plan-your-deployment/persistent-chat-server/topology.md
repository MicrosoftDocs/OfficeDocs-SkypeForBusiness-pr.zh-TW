---
title: 規劃 Persistent Chat Server 拓撲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：閱讀此主題以瞭解商務用 Skype 2015 Server 中的持久聊天伺服器元件和拓撲。
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825503"
---
# <a name="plan-persistent-chat-server-topology"></a>規劃 Persistent Chat Server 拓撲
 
**摘要：** 閱讀此主題以瞭解商務用 Skype 2015 Server 中的持久聊天伺服器元件和拓撲。
  
Persistent Chat Server 同時支援單一伺服器和多部伺服器設定。 您可以在商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition Server 上安裝 Persistent Chat Server。 

> [!NOTE] 
> 商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。 小組中提供相同的功能。 如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。 
  
## <a name="persistent-chat-server-components"></a>Persistent Chat Server 元件

Persistent Chat Server 包含下列元件：
  
- 一或多部執行 Persistent Chat Server 的電腦，並提供下列服務：
    
  - Persistent Chat service
    
  - 規範服務，會在啟用規範時開啟
    
- 如果使用鏡像，一或多部伺服器 (一或多部) 執行 SQL Server 後端資料庫，以主控存放聊天室內容、會議室及類別的持久聊天內容資料庫。
    
    > [!NOTE]
    > 後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的資訊。 
  
- 如果已啟用相容性，一或多部伺服器 (會使用鏡像) 執行 SQL Server 後端資料庫，以裝載 Persistent 聊天室規範資料庫，以儲存相容性事件和聊天內容的目的。
    
如需有關 Persistent Chat Server 的硬體和軟體需求的詳細資訊，請參閱商務用 skype server 2015 中 [的商務用 Skype server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 和 [硬體和軟體需求的](hardware-and-software-requirements.md)伺服器需求。 
  
## <a name="persistent-chat-server-topologies"></a>Persistent Chat Server 拓撲

您可以在單一伺服器或多部伺服器集區中部署 Persistent Chat Server，並使用單一集區或多集區拓撲。 Persistent Chat Server 支援下列拓撲：
  
-  前端伺服器上具有 Persistent Chat Server 組合的 Standard Edition Server
    
-  個別伺服器上具有 Persistent Chat Server 的 Standard Edition Server
    
-  在不同伺服器上具有單一持久聊天伺服器的 Enterprise Edition Server
    
-  在不同伺服器上有多部 Persistent Chat Server 的 Enterprise Edition Server
    
雖然您可以在 Standard Edition Server 上部署 Persistent Chat Server，但請注意，效能及規模會受到影響，而高可用性不是選項。 因此，建議您在 Standard Edition Server 上部署持續性聊天，主要是用來做為概念證明和評估目的。 
  
商務用 Skype Server 2015 可支援各種組合案例，為您提供彈性，您可以在一部伺服器上執行多個元件，以在一部伺服器)  (上執行多個元件，或在不同的伺服器上執行個別元件 (如果您有較大的組織需要可擴充性和效能) 。 您應考慮可伸縮性因素，再決定是否要組合元件。 適用于商務用 Skype Server 2015 Enterprise Edition 和 Standard Edition server 的組合案例各有不同。 
  
下列各節將更詳細地說明拓撲，包括後端資料庫伺服器的組合案例和選項。 如需組合所有伺服器角色及資料庫的詳細資訊，請參閱 [商務用 Skype server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>前端伺服器上具有 Persistent Chat Server 組合的 Standard Edition Server

使用 Standard Edition，您可以在前端伺服器上組合持久聊天。 這是最簡單和最基本的設定。 您必須確定現有的前端伺服器在實體資源方面具有足夠的容量： CPU、記憶體、磁碟空間等等。
  
此外，您也可以在本機 SQL Server Express 後端伺服器上組合持久的 Chat Server 後端伺服器和 Persistent Chat database (（如果已啟用) ）。 您也可以選擇使用個別的 SQL Server 搭配專用的實例。 
  
> [!IMPORTANT]
> 如果第一個 Persistent Chat Server 是以 Standard Edition 前端伺服器組合，您就無法將其他伺服器新增至 Persistent Chat Server 集區。 建議您安裝第一部伺服器做為獨立實例，以便在需要時新增更多的伺服器。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>在不同的伺服器上安裝具有 Persistent Chat Server 的 Standard Edition Server

使用 Standard Edition，您可以將 Persistent Chat Server 安裝為獨立實例，並在以後必要時新增更多伺服器。 
  
您可以在本機 SQL Server Express 後端伺服器上組合持久聊天伺服器後端伺服器和 Persistent Chat 合規性資料庫 (（如果已啟用）) 。 您也可以選擇使用個別的 SQL Server 搭配專用的實例。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>單一持久聊天伺服器的 Enterprise Edition Server

搭配 Enterprise Edition，您必須在不同的電腦上安裝 Persistent Chat Server。 也就是說，您無法在 Enterprise Edition 前端伺服器上組合 Persistent Chat Server。 此部署需要執行 Persistent Chat Server 和合規性服務 (的個別伺服器（如果已啟用) ）。
  
不過，您可以在 Enterprise Edition 前端集區的後端資料庫上，組合適用于 Persistent Chat Server 的 SQL Server 資料庫。
  
> [!NOTE]
> 如果您打算使用 SQL AlwaysOn 可用性群組進行 HA DR，請注意，Persistent Chat Server 資料庫不支援此功能。 
  
如果您使用後端資料庫組合 Persistent Chat 資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，也可以針對每個資料庫使用不同的 SQL Server 實例。
  
> [!IMPORTANT]
> 主控 Persistent Chat 資料庫的伺服器可以主控其他資料庫。 不過，當您考慮將 Persistent Chat 資料庫與其他資料庫組合時，請注意，如果您儲存的是少數幾個使用者的郵件，則 Persistent Chat 資料庫所需的磁碟空間會變得非常大。 基於這個理由，我們不建議組合 Persistent Chat 資料庫與後端資料庫。 
  
下圖顯示單一 Persistent Chat Server 的拓撲的所有元件（啟用相容性 (選用) ）。
  
**單一伺服器拓撲**

![Persistent Chat Server-單一伺服器拓撲](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>具有多個 Persistent 聊天伺服器的 Enterprise Edition Server

使用 Enterprise Edition，您可以部署多部伺服器拓撲，以取得更大的容量和可靠性。 多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。 多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。 每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。 多部執行 Persistent Chat Server 的電腦應該位於與商務用 Skype Server 和合規性服務相同的 Active Directory 網域服務網域中。
  
下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。
  
**多伺服器拓撲**

![Persistent Chat Server-多部伺服器拓撲](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多伺服器拓撲提供伺服器功能的集區。 在伺服器集區中，Persistent Chat service 會通訊和共用資料。 例如，您可以從系統中的任何 Persistent Chat service 取得最初發佈到某項 Persistent Chat service 的聊天記錄。 任何 Persistent chat service 都可以存取透過某項 Persistent Chat service 上傳的檔案。 使用者可以連線至不同的持久聊天伺服器前端伺服器，也可以相互通訊。 TCP 8011 的預設埠會將伺服器連線至伺服器集區，而 Persistent Chat service 會使用該埠自身進行通訊，或用於管理目的。
  
例如，在四部伺服器的持續聊天伺服器部署中，80000使用者可以同時登入持久聊天，此負載會在每一部伺服器的20000使用者上平均分配。 如果一部伺服器無法使用，連接至該伺服器的使用者將無法存取其 Persistent Chat Server。 連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。 
  

