---
title: 安裝 Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要： 了解如何準備 Business Server 安裝的 Skype 環境。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: e33e773abf25be92c163de259af0c3f47e0b1783
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042380"
---
# <a name="install-skype-for-business-server"></a>安裝 Skype for Business Server
 
**摘要：** 了解如何準備 Business Server 安裝的 Skype 環境。 下載 Microsoft 評估管理中心，從 Business Server Skype 免費試用版：[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
這篇文章引導您逐步完成 Skype 範例安裝 Business server。 本文不會嘗試涵蓋所有您需要執行完整的 Skype for Business Server 安裝程序。 目標是要提供範例程序中的窄定義拓撲，包括基本開會及共用功能。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Skype 商務伺服器安裝程序的概觀

Skype for Business Server 安裝包含許多不同的程序。 您需要取得 Skype for Business Server 環境中執行的程序取決於您的環境的細節。 例如，如果您使用 Windows Server 的 DNS，您會受益於範例程序新增 DNS 項目。 如果您使用另一個系統 DNS，您必須遵循特定的 DNS 系統的程序。 這是許多本節中的程序，則為 true。
  
在 Standard Edition 及 Enterprise Edition 中使用商務用 Skype 商務伺服器。 主要差異是，Standard Edition 不支援隨附 Enterprise Edition 的高可用性功能。 
  
Skype 商務 Server 是進階的產品，並完全安裝程序取決於許多您特定的情況。 本節引導您逐步完成安裝產品的一般步驟。 不過，每項程序可能會因您的環境和規劃決策。 例如，用於小型組織的單一伺服器，執行 Skype for Business Server Standard Edition 可能適用，而大型的多語系組織可能有 50 伺服器專用於產品在世界各地的位置。
  
> [!NOTE]
> 若要了解最新的累計更新，請參閱[Skype for Business Server 更新](https://support.microsoft.com/kb/3061064)。 在安裝 CU1 修補程式完成後系統管理員必須執行`Update-CsAdminRole`指令程式。 此指令程式，才能透過遠端 PowerShell 存取新的 GCP cmdlet。
  
> [!IMPORTANT]
> 本節中的程序做為使用一組窄定義的需求的範例，並假設已進行特定的決策。 您要安裝 Skype for Business 伺服器的實際程序可能會很大的差異。 使用程序在本節中做為唯一範例，而不是逐步指南的每個環境中安裝 Skype for Business Server。 
  
取得 Skype for Business Server 及第一次執行涉及八個主要步驟。 您應該了解這一節中的範例程序不會安裝 Skype for Business Server 所需的唯一程序。 下列的八個步驟是只需範例，以協助您更加了解整體程序，並取得基本使用環境和執行。 您可以執行步驟 1 到 5，以任何順序。 不過，您必須先執行步驟 6、 7 和 8 順序，並在步驟 1 到 5 之後，在圖表中所述。 八個步驟如下：
  
![安裝程序的概觀。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安裝 Skype for Business Server 的必要條件](install-prerequisites.md)： 構成 Skype for Business Server 拓撲的所有伺服器上安裝必要條件。 請注意，必要條件不是相同的所有角色。 例如，提供前端角色的伺服器有一組的必要條件，並提供 director 角色的伺服器有一組不同的必要條件。 必要的規劃文件，如需詳細資訊，請參閱。
    
- [建立檔案共用 skype for Business Server](create-a-file-share.md) ： 建立將用於整個 Skype 伺服器的企業伺服器拓撲的檔案共用。
    
- [安裝系統管理工具] skype for Business Server](install-administrative-tools.md) ： 系統管理工具包括拓撲產生器] 及 [控制台]。 您必須至少一部伺服器拓撲或執行支援 skype for Business Server 的 Windows 作業系統版本的 64 位元管理工作站上安裝的系統管理工具。
    
- [準備 Active Directory 中的 Skype for Business Server](prepare-active-directory.md) : Skype for Business Server 密切合作，與 Active Directory。 您必須先準備 Active Directory 網域，才能使用 Skype for Business Server。 您可以透過 [部署精靈]，它只都會執行一次的網域。 這是因為和處理程序會建立群組，並修改的網域，您需要執行動作的唯一一次。
    
- [Skype 商務伺服器建立 DNS 記錄](create-dns-records.md)： 為了 skype 商務伺服器才能正常運作的 DNS 設定的數字必須就緒。 這是，讓用戶端知道 how to： 存取服務和伺服器彼此需注意的事項。 這些設定只需要完成一次每個部署因為之後您指派的 DNS 項目時，會有整個網域。
    
- [建立及發佈新拓撲 skype for Business Server](create-and-publish-new-topology.md) ： 您可以在各種拓撲中的伺服器上安裝 Skype for Business Server 系統之前，您必須建立拓撲，並將它發佈。 當您發佈拓撲時，您正在載入的拓撲資訊到中央管理存放區資料庫。 如果這是 Enterprise Edition 集區，您正在建立發行新拓撲中央管理存放區資料庫第一次。 如果這是標準版，您需要執行 [部署精靈準備第一個 Standard Edition Server 處理程序，才能發行拓撲。 這會準備 Standard Edition 安裝 SQL Server Express Edition 執行個體，並建立中央管理存放區。
    
- [安裝儲存企業伺服器拓撲中的伺服器上的商務用 Skype](install-skype-for-business-server.md) ： 一旦拓撲載入至中央管理存放區及 Active Directory 知道哪些伺服器將會執行哪些角色，您需要在每個拓撲中的伺服器上安裝 Skype for Business Server 系統。
    
- [確認 skype for Business 伺服器拓撲](verify-the-topology.md)： 發佈拓撲與 Skype for Business Server 系統元件每一部伺服器拓撲中安裝之後，您已準備好確認拓撲是否如預期運作。 這包括驗證的組態已傳播出的所有 Active Directory 伺服器使整個網域知道商務用 Skype 是可用的網域中。
    

