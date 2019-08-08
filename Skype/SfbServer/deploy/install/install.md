---
title: 安裝商務用 Skype Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: '摘要: 瞭解如何在安裝商務用 Skype Server 時準備您的環境。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: f15a305a660586e017984a171db217636e2e09ff
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244334"
---
# <a name="install-skype-for-business-server"></a>安裝商務用 Skype Server
 
**摘要:** 瞭解如何在安裝商務用 Skype Server 時準備您的環境。 從 Microsoft 評估中心下載免費試用版商務用 Skype Server, 網址為:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
本文將引導您完成商務用 Skype Server 的安裝範例。 本文不會嘗試涵蓋執行完整商務用 Skype Server 安裝所需的所有程式。 其目標是在定義的拓撲中提供範例程式, 其中包含基本的 [會見與共享] 功能。
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>商務用 Skype Server 的安裝程式概覽

安裝商務用 Skype Server 包含許多不同的程式。 在您的環境中執行商務用 Skype 伺服器所需的程式, 取決於您的環境細節。 例如, 如果您使用的是 DNS 的 Windows Server, 您將能從新增 DNS 專案的範例程式獲益。 如果您使用其他的 DNS 系統, 您必須遵循特定 DNS 系統的程式。 此區段中的許多程式都是如此。
  
商務用 Skype 伺服器可在標準版和企業版中使用。 主要差異是標準版不支援企業版中包含的高可用性功能。 
  
商務用 Skype Server 是一種先進的產品, 而確切的安裝程式則取決於您特定的情況。 本節會逐步引導您完成安裝產品的一般步驟。 不過, 根據您的環境和規劃決定, 每個程式可能會有所不同。 例如, 對於小型組織而言, 執行商務用 Skype Server Standard Edition 可能是適當的, 而大型跨國公司組織可能會在全球各地專用於產品的50伺服器。
  
> [!NOTE]
> 若要瞭解最新的累計更新, 請參閱[商務用 Skype Server 更新](https://support.microsoft.com/en-us/kb/3061064)。 安裝 CU1 修補程式後, 系統管理員必須執行`Update-CsAdminRole` Cmdlet。 需要使用此 Cmdlet 來存取遠端 PowerShell 中的新 GCP Cmdlet。
  
> [!IMPORTANT]
> 此區段中的程式是使用一組定義的需求, 並假設已經進行特定決策的範例。 安裝商務用 Skype Server 所需的實際程式可能會有很大的差異。 在每個環境中, 請使用本節中的程式做為範例, 而不是作為安裝商務用 Skype Server 的逐步指南。 
  
第一次取得商務用 Skype 伺服器並執行的步驟包括八個主要步驟。 您應該瞭解本節中的範例程式不是安裝商務用 Skype Server 所需的唯一程式。 下列八個步驟只是協助您進一步瞭解整個程式, 並讓基本工作環境正常運作的範例。 您可以依照任何循序執行步驟1到5。 不過, 您必須在順序中執行步驟6、7和 8, 並在步驟1到5之後, 如圖表中所述。 8個步驟如下:
  
![安裝程式的概覽。](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [安裝商務用 Skype server 的先決條件](install-prerequisites.md): 在組成商務用 skype server 拓撲的所有伺服器上安裝系統必備。 請注意, 所有角色的先決條件都不相同。 例如, 提供前端角色的伺服器會有一組先決條件, 而提供主管角色的伺服器則具有不同的先決條件組。 如需詳細資訊, 請參閱必備元件規劃檔。
    
- [在商務用 Skype server 中建立檔案共用](create-a-file-share.md): 建立將在整個商務用 skype server 拓撲結構中供伺服器使用的檔案共用。
    
- [在商務用 Skype Server 中安裝系統管理工具](install-administrative-tools.md): 管理工具組括拓撲建立器和 [控制台]。 您必須在拓撲中至少有一個伺服器上安裝管理工具, 或是在執行商務用 Skype Server 支援的 Windows OS 版本的64位管理工作站。
    
- [為商務用 Skype Server 準備 Active directory](prepare-active-directory.md) : 商務用 skype 伺服器與 Active directory 密切搭配使用。 您必須準備 Active Directory 網域, 才能搭配商務用 Skype 伺服器使用。 您可以透過 [部署嚮導] 來執行此動作, 而且只會針對網域進行一次。 這是因為程式會建立群組並修改網域, 而您只需要執行一次。
    
- [建立商務用 Skype server 的 DNS 記錄](create-dns-records.md): 若要讓商務用 skype 伺服器正常運作, 必須有許多 DNS 設定。 這是為了讓客戶知道如何存取服務, 以及伺服器彼此瞭解的相關資訊。 這些設定只需要針對每個部署完成一次, 因為指派 DNS 專案之後, 就能在整個網域中使用它。
    
- [在商務用 Skype server 中建立及發佈新的拓朴](create-and-publish-new-topology.md): 您必須先建立拓撲併發布, 才能在拓撲中的每個伺服器上安裝商務用 skype server 系統。 當您發佈拓撲時, 會將拓撲資訊載入到中央管理儲存資料庫中。 如果這是企業版文件庫, 當您第一次發佈新的拓撲時, 就會建立中央管理儲存資料庫。 如果這是標準版, 您必須先從 [部署嚮導] 執行 [準備第一個標準版伺服器] 程式, 然後才能發佈拓撲。 這是為了準備標準版本, 只要安裝 SQL Server Express Edition 實例並建立中央管理儲存。
    
- 在[拓撲中的伺服器上安裝商務用 Skype Server](install-skype-for-business-server.md) : 一旦將拓撲載入到中央管理儲存體, 且 Active Directory 知道哪些伺服器將會執行哪些角色, 您必須在每個伺服器上安裝商務用 skype server 系統拓撲中的伺服器。
    
- [在商務用 Skype server 中驗證拓朴](verify-the-topology.md): 當您已發佈拓撲, 且已在拓撲結構中的每個伺服器上安裝商務用 Skype Server system 元件之後, 您就可以開始確認拓撲結構是否如預期一樣運作。 這包括驗證設定是否已傳播到所有的 Active Directory 伺服器, 讓整個網域知道該網域中的商務用 Skype。
    

