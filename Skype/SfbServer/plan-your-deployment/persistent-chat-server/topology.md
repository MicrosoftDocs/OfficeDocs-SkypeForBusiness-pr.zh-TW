---
title: 規劃常設聊天室伺服器拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：請閱讀本主題，瞭解商務用 Skype Server 2015 中的持續聊天伺服器元件與拓撲。
ms.openlocfilehash: afcdf7ed85cca6b54652dcf5170316258a6b5551
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815721"
---
# <a name="plan-persistent-chat-server-topology"></a>規劃常設聊天室伺服器拓撲
 
**摘要：** 閱讀本主題以瞭解商務用 Skype Server 2015 中的持續聊天伺服器元件與拓撲。
  
持續聊天伺服器支援單伺服器和多伺服器設定。 您可以在商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition Server 上安裝持續聊天伺服器。 

> [!NOTE] 
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 
  
## <a name="persistent-chat-server-components"></a>持續聊天伺服器元件

持續聊天伺服器包含下列元件：
  
- 一或多台執行持續聊天伺服器且提供下列服務的電腦：
    
  - 持續聊天服務
    
  - 相容性服務，在啟用合規性時開啟
    
- 一或多個伺服器（如果使用鏡像的話的話），會執行 SQL Server 後端資料庫，以託管存放聊天室內容、會議室及類別的持續聊天內容資料庫。
    
    > [!NOTE]
    > 後端資料庫會儲存聊天記錄資料，包括所建立之類別和持續聊天室的相關資訊。 
  
- 如果已啟用相容性，則會使用一或多個伺服器（如果使用鏡像的話的話），執行 SQL Server 後端資料庫來託管持續性聊天相容性資料庫，並儲存合規性事件和聊天內容以滿足規範的目的。
    
如需持續式聊天伺服器的硬體和軟體需求的詳細資訊，請參閱商務用 skype server 2015 中[的商務用 Skype server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)與[硬體及軟體需求（商務用 skype server](hardware-and-software-requirements.md)）。 
  
## <a name="persistent-chat-server-topologies"></a>持續聊天伺服器拓撲

您可以在單一伺服器或多重伺服器池中部署持久聊天伺服器，以及使用單一池或多池拓撲。 持續聊天伺服器支援下列拓撲：
  
-  前端伺服器上具有持續聊天伺服器 collocated 的標準版伺服器
    
-  在個別伺服器上使用持續聊天伺服器的標準版伺服器
    
-  在個別伺服器上使用單一持久聊天伺服器的企業版伺服器
    
-  在個別伺服器上有多個持續聊天伺服器的企業版伺服器
    
雖然您可以在標準版伺服器上部署持續性聊天伺服器，但請注意，效能和規模會受到影響，且不提供高可用性選項。 因此，建議您在標準版伺服器上部署持續聊天，主要是為了提供概念和評估用途。 
  
商務用 Skype Server 2015 支援各種不同的 collocation 案例，可讓您靈活地在一部伺服器（如果您有小型組織）上執行多個元件，或在不同的伺服器上執行個別元件，以節省硬體成本。如果您的組織規模較大，且需要伸縮性和效能，請使用此選項。 在決定是否要 collocate 元件之前，您應該先考慮可伸縮性因素。 商務用 Skype Server 2015 Enterprise Edition 和 Standard Edition 伺服器的 Collocation 案例有所不同。 
  
下列各節將更詳細說明拓撲，包括後端資料庫伺服器的 collocation 案例和選項。 如需 collocation 所有伺服器角色和資料庫的詳細資料，請參閱[商務用 Skype server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>前端伺服器上具有持續聊天伺服器 collocated 的標準版伺服器

在標準版中，您可以在前端伺服器上 collocate 持續聊天。 這是最簡單且最基本的配置。 您必須確認現有的前端伺服器具有足夠的容量，就像是 CPU、記憶體、磁碟空間等。
  
此外，您也可以在本機 SQL Server Express 後端伺服器上，collocate 持續式聊天伺服器後端伺服器和持續性聊天規範資料庫（如果已啟用的話）。 您也可以選擇將個別的 SQL 伺服器與專用實例搭配使用。 
  
> [!IMPORTANT]
> 如果第一個持久聊天伺服器是與標準版前端伺服器 collocated，則您無法將其他伺服器新增至持久聊天伺服器池。 建議您將第一個伺服器安裝為獨立實例，以便日後在需要時新增更多伺服器。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>在個別伺服器上安裝持久聊天伺服器的標準版伺服器

在標準版中，您可以將持續性聊天伺服器安裝為獨立實例，並視需要新增更多伺服器。 
  
您可以在本機 SQL Server Express 後端伺服器上，collocate 持續式聊天伺服器後端伺服器和持續性聊天規範資料庫（如果已啟用的話）。 您也可以選擇將個別的 SQL 伺服器與專用實例搭配使用。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>具備單一持久聊天伺服器的企業版伺服器

在 [企業版] 中，您必須在另一部電腦上安裝永久聊天伺服器。 也就是說，您無法在企業版前端伺服器上 collocate 永久聊天伺服器。 此部署需要獨立的伺服器來執行持續聊天伺服器與合規性服務（如果已啟用的話）。
  
不過，您可以在企業版前端池的後端資料庫上，collocate [SQL Server 資料庫]，以取得持續聊天伺服器。
  
> [!NOTE]
> 如果您打算針對 HA 災害復原使用 SQL AlwaysOn 可用性群組，請注意，持久聊天伺服器資料庫不支援此功能。 
  
如果您 collocate 與後端資料庫的持續聊天資料庫，您可以針對任何或所有資料庫使用單一的 SQL Server 實例，或者您可以針對每個資料庫使用個別的 sql Server 實例。
  
> [!IMPORTANT]
> 主持持久聊天資料庫的伺服器可以裝載其他資料庫。 不過，當您考慮將持續聊天資料庫與其他資料庫 collocating 時，請注意，如果您要儲存的訊息超過幾個使用者，持久聊天資料庫所需的磁碟空間可能會變得很大。 基於這個原因，我們不建議您 collocating 與後端資料庫的持續聊天資料庫。 
  
下圖顯示已啟用合規性（選用）之單一持久聊天伺服器的拓撲所有元件。
  
**單一伺服器拓朴**

![持續聊天伺服器-單一伺服器拓撲](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>具有多個持續聊天伺服器的企業版伺服器

在企業版中，您可以部署多重伺服器拓撲結構，以獲得更大的容量與可靠性。 多重伺服器拓朴與單一伺服器拓朴一樣，只是多個伺服器主機持久的聊天伺服器，而且可以擴大規模。 多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦（高可用性和災害復原設定允許最多八個，但只有四個作用中的4個作用中，還有四個作用中的四個）。 每個伺服器可支援多達20000並行的使用者，總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。 多台執行持續聊天伺服器的電腦應該位於與商務用 Skype Server 及合規性服務相同的 Active Directory 網域服務網域中。
  
下圖顯示多伺服器拓朴中的所有元件，其中多台電腦執行持續聊天伺服器、選用規範服務，以及個別的合規性資料庫。
  
**多個伺服器拓朴**

![持續聊天伺服器-多重伺服器拓撲](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
多伺服器拓朴提供伺服器功能的彙集。 在伺服器池中，持續聊天服務會與資料進行通訊和共用。 例如，您可以從系統中的任何持續聊天服務取得最初張貼到一個持續聊天服務的聊天記錄。 透過一個持久聊天服務上傳的檔案，可透過任何持續聊天服務存取。 使用者可以連線至不同的持續聊天伺服器前端伺服器，而且可以彼此通訊。 TCP 8011 的預設埠會將伺服器連線到伺服器池中，且持續聊天服務會使用它來溝通，或針對管理目的進行通訊。
  
例如，在四個伺服器持續式聊天伺服器部署中，80000使用者可以同時登入持續聊天，在每個伺服器上，都會將負載平均分佈在20000個使用者。 如果一個伺服器無法使用，則連接至該伺服器的使用者將無法存取永久聊天伺服器。 已中斷連線的使用者會自動轉移到其餘的伺服器，直到無法還原無法使用的伺服器為止。 
  

