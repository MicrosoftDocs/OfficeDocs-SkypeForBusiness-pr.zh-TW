---
title: 安裝商務用 Skype Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: 摘要：瞭解如何準備您的環境，以安裝商務用 Skype Server。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: 997dc590030e27305058bd4e2bb6773d1114d597276404f23ae350a899666b03
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323495"
---
# <a name="install-skype-for-business-server"></a>安裝商務用 Skype Server
 
**摘要：** 瞭解如何準備您的環境，以安裝商務用 Skype Server。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
本文將引導您完成商務用 Skype Server 的安裝範例。 本文不會嘗試涵蓋執行完整商務用 Skype Server 安裝所需的所有程式。 目標是在定義的拓撲中提供範例程式，該拓撲包含基本的符合和共用功能。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>商務用 Skype Server 安裝程式的概覽

安裝商務用 Skype Server 包含許多不同的程式。 您在環境中執行商務用 Skype Server 所需的程式取決於您的環境細節。 例如，如果您使用 Windows 的 dns 伺服器，您將會受益于新增 dns 專案的範例程式。 如果您為 DNS 使用另一個系統，您必須遵循特定 DNS 系統的程式。 本節中的許多程式都是如此。
  
Standard Edition 和 Enterprise Edition 可使用商務用 Skype Server。 主要差異是 Standard Edition 不支援 Enterprise Edition 附帶的高可用性功能。 
  
商務用 Skype Server 是一種高級產品，確切的安裝程式會在您特定的情況中非常重要。 本節會引導您完成安裝產品的一般步驟。 不過，每個程式可能會因環境和規劃決策而異。 例如，針對小型組織的單一伺服器，執行商務用 Skype Server Standard Edition 可能是適當的，而大型的跨國組織可能會在世界各地專用於產品的50伺服器。
  
> [!NOTE]
> 若要瞭解最新的累計更新，請參閱[更新商務用 Skype Server](https://support.microsoft.com/kb/3061064)。 安裝 CU1 修補程式後，系統管理員必須執行  `Update-CsAdminRole` Cmdlet。 此 Cmdlet 是透過遠端 PowerShell 存取新的 GCP Cmdlet 所需。
  
> [!IMPORTANT]
> 本節中的程式是使用一組豐富定義的需求，並假設已經進行特定決策的範例。 安裝商務用 Skype Server 所需的實際程式可能會有很大的差異。 請使用本節中的程式做為範例，而不是逐步指南，以在每個環境中安裝商務用 Skype Server。 
  
第一次取得商務用 Skype Server 及執行的步驟包含8個主要步驟。 您應該瞭解本節中的範例程式不是安裝商務用 Skype Server 所需的程式。 下列八個步驟只是一些範例，可協助您更好地瞭解整體程式，並讓基本運作環境啟動且正常運作。 您可以依任何循序執行步驟1到5。 不過，您必須依序執行步驟6、7和8，並在步驟1到5之後進行，如圖表中所述。 這八個步驟包括：
  
![安裝程式的概述。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安裝商務用 Skype Server 的必要條件](install-prerequisites.md)：在組成商務用 Skype Server 拓撲的所有伺服器上安裝必要條件。 請注意，所有角色的必要條件都不相同。 例如，提供前端角色的伺服器具有一組必要條件，而提供 director 角色的伺服器則具有一組不同的必要條件。 如需詳細資訊，請參閱必要的規劃檔。
    
- [在商務用 Skype Server 中建立檔案共用](create-a-file-share.md)：建立整個商務用 Skype Server 拓撲中的伺服器所使用的檔案共用。
    
- [在商務用 Skype Server 中安裝系統管理工具](install-administrative-tools.md)：系統管理工具組括拓撲產生器和控制台。 您必須在拓撲中至少一部伺服器上安裝系統管理工具，或在執行商務用 Skype Server 支援 Windows OS 版本的64位管理工作站上安裝系統管理工具。
    
- [為商務用 Skype Server 準備 Active directory](prepare-active-directory.md) ：商務用 Skype Server 與 active directory 密切搭配使用。 您必須準備作用中的 Active Directory 網域，才能使用商務用 Skype Server。 您可以透過部署嚮導來執行這項作業，只會對網域執行一次。 這是因為程式會建立群組並修改網域，而您只需要執行一次。
    
- [為商務用 Skype Server 建立 dns 記錄](create-dns-records.md)：為了讓商務用 Skype Server 能夠正常運作，必須有許多 dns 設定。 如此一來，用戶端就知道如何存取彼此相關的服務和伺服器。 這些設定只需要在每次部署時完成一次，因為一旦您指派 DNS 專案，它就會可用於整個網域。
    
- [在商務用 Skype Server 中建立及發行新的拓撲](create-and-publish-new-topology.md)：在拓撲的每一部伺服器上安裝商務用 Skype Server 系統之前，必須先建立拓撲並加以發佈。 發行拓撲時，會將拓撲資訊載入至中央管理存放區資料庫。 如果這是 Enterprise Edition 集區，則在第一次發行新的拓撲時，您會建立中央管理存放區資料庫。 如果這是 Standard Edition，您必須先從部署嚮導執行第一 Standard Edition 伺服器處理常式，再發佈拓撲。 這為 Standard Edition 準備安裝 SQL Server Express Edition 實例和建立中央管理存放區。
    
- 在[拓撲中的伺服器上安裝商務用 Skype Server](install-skype-for-business-server.md) ：將拓撲載入至中央管理存放區，並使用 Active Directory 知道哪些伺服器會執行哪些角色，您必須在拓撲中的每一部伺服器上安裝商務用 Skype Server 系統。
    
- [驗證商務用 Skype Server 中的拓撲](verify-the-topology.md)：在您已發行拓撲之後，在拓撲中的每一部伺服器上安裝商務用 Skype Server 系統元件之後，就可以確認拓撲的運作如預期般運作。 這包括驗證設定是否已向內傳播至所有 Active Directory 伺服器，讓整個網域知道商務用 Skype 可用於網域。
    

