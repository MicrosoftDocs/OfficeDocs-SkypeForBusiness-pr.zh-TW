---
title: 安裝商務用 Skype Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要：瞭解如何準備環境以安裝商務用 Skype Server。
ms.openlocfilehash: 32003fc1c269a0bf1b59afc965099851b6406ed6
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860584"
---
# <a name="install-skype-for-business-server"></a>安裝商務用 Skype Server
 
**總結：** 瞭解如何準備環境以安裝商務用 Skype Server。
  
本文將逐步引導您完成範例安裝商務用 Skype Server。 本文不會嘗試涵蓋執行完整商務用 Skype Server安裝所需的所有程式。 目標是在包含基本符合和共用功能的窄定義拓撲中提供範例程式。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>商務用 Skype Server的安裝程式概觀

商務用 Skype Server的安裝包含許多不同的程式。 您需要取得商務用 Skype Server在環境中執行的程式，取決於您環境的特性。 例如，如果您使用 Windows Server for DNS，您將受益于新增 DNS 專案的範例程式。 如果您針對 DNS 使用另一個系統，則必須遵循特定 DNS 系統的程式。 這適用于本節的許多程式。
  
商務用 Skype Server可在 Standard Edition 和 Enterprise Edition 中取得。 主要差異在於Standard Edition不支援Enterprise Edition隨附的高可用性功能。 
  
商務用 Skype Server是進階產品，而確切的安裝程式取決於您的特定情況。 本節將逐步引導您完成安裝產品的一般步驟。 不過，每個程式可能會根據您的環境和規劃決策而有所不同。 例如，對於小型組織而言，執行商務用 Skype Server Standard Edition的單一伺服器可能很適合，而大型跨國組織可能在全球各地的產品專用位置有 50 部伺服器。
  
> [!NOTE]
> 若要瞭解最新的累積更新，請參閱[商務用 Skype Server的更新](https://support.microsoft.com/kb/3061064)。 安裝 CU1 修補程式之後，系統管理員必須執行 Cmdlet  `Update-CsAdminRole` 。 需要此 Cmdlet 才能透過遠端 PowerShell 存取新的 GCP Cmdlet。
  
> [!IMPORTANT]
> 本節中的程式是使用一組以窄定義的需求做為範例，並假設已經做出特定決策。 您需要安裝商務用 Skype Server的實際程式可能會非常不同。 僅使用本節中的程式做為範例，而不是在每個環境中安裝商務用 Skype Server的逐步指南。 
  
第一次啟動並執行商務用 Skype Server包含八個主要步驟。 您應該瞭解本節中的範例程式不是安裝商務用 Skype Server所需的唯一程式。 下列八個步驟只是範例，可協助您進一步瞭解整體程式，並讓基本的工作環境啟動並執行。 您可以依任何循序執行步驟 1 到 5。 不過，您必須依序執行步驟 6、7 和 8，以及步驟 1 到 5 之後，如圖表中所述。 八個步驟如下：
  
![安裝程式概觀。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安裝商務用 Skype Server的必要](install-prerequisites.md)條件：在組成商務用 Skype Server拓撲的所有伺服器上安裝必要條件。 請注意，所有角色的必要條件並不相同。 例如，提供前端角色的伺服器有一組必要條件，而提供目錄角色的伺服器則有一組不同的必要條件。 如需詳細資訊，請參閱必要條件規劃檔。
    
- [在 商務用 Skype Server 中建立檔案共用](create-a-file-share.md)：建立伺服器將在整個商務用 Skype Server拓撲中使用的檔案共用。
    
- [在 商務用 Skype Server 中安裝系統管理工具](install-administrative-tools.md)：系統管理工具組括拓撲產生器和主控台。 您必須在拓撲中的至少一部伺服器上安裝系統管理工具，或在執行商務用 Skype Server支援之 Windows OS 版本的 64 位管理工作站上安裝。
    
- [準備 Active Directory 以商務用 Skype Server](prepare-active-directory.md)：商務用 Skype Server與 Active Directory 密切合作。 您必須準備 Active Directory 網域才能使用商務用 Skype Server。 您可以透過 [部署精靈] 來執行此動作，而且只會針對網域執行一次。 這是因為程式會建立群組並修改網域，而且您只需要執行一次。
    
- [建立商務用 Skype Server的 DNS 記錄](create-dns-records.md)：為了讓商務用 Skype Server正常運作，必須備妥一些 DNS 設定。 這可讓用戶端知道如何存取服務，以及伺服器彼此瞭解。 每個部署只需要完成這些設定一次，因為一旦您指派 DNS 專案，就可以在整個網域中使用。
    
- [在 商務用 Skype Server 中建立和發佈新的拓](create-and-publish-new-topology.md)撲：在拓撲的每個伺服器上安裝商務用 Skype Server系統之前，您必須先建立拓撲並加以發佈。 當您發佈拓撲時，會將拓撲資訊載入中央管理Microsoft Store資料庫。 如果這是Enterprise Edition集區，您會在第一次發佈新拓撲時建立中央管理Microsoft Store資料庫。 如果Standard Edition，您必須先從 [部署精靈] 執行 [準備第一個Standard Edition伺服器] 程式，才能發佈拓撲。 這會藉由安裝 SQL Server Express Edition 實例並建立中央管理Microsoft Store來準備Standard Edition。
    
- [在拓撲的伺服器上安裝商務用 Skype Server](install-skype-for-business-server.md)：將拓撲載入中央管理Microsoft Store，且 Active Directory 知道哪些伺服器會執行哪些角色，您必須在拓撲的每部伺服器上安裝商務用 Skype Server系統。
    
- [確認商務用 Skype Server中的拓](verify-the-topology.md)撲：在您發佈拓撲，並在拓撲的每部伺服器上安裝商務用 Skype Server系統元件之後，您就可以確認拓撲是否如預期般運作。 這包括確認組態已傳播至所有 Active Directory 伺服器，讓整個網域知道網域中有可用的商務用 Skype。
    

