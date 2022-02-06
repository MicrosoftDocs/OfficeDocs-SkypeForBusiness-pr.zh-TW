---
title: 建立資料庫
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 拓撲產生器提供一種方法，可在 SQL Server 儲存區上安裝資料庫。 當您使用拓撲產生器安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 叢集上安裝必要的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或是必須安裝組合資料庫，則必須改用 Windows PowerShell 命令列介面和 Install-CsDatabase Cmdlet。
---

# <a name="create-database"></a>建立資料庫
 
拓撲產生器提供一種方法，可在 SQL Server 儲存區上安裝資料庫。 當您使用拓撲產生器安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 叢集上安裝必要的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或是必須安裝組合資料庫，則必須改用 Windows PowerShell 命令列介面和[Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) Cmdlet。
  
### <a name="creating-a-database"></a>建立資料庫

1. 按一下 [商務用 Skype Server] 節點，然後按一下 [**安裝資料庫**]。
    
2. 在 [**安裝** 資料庫] 對話方塊的 [**建立資料庫**] 頁面上，選取要用來建立新資料庫之 SQL Server 存放區的完整功能變數名稱 (FQDN) 。
    
3. 按一下 [進階]。在 [選取資料庫檔案位置] 對話方塊中，選取下列其中一個選項：
    
   - **自動判斷資料庫檔案位置**。選取此選項時，拓撲產生器會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。
    
   - **使用 SQL Server 執行個體預設值**。 選取此選項時，不會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。 相反地，記錄檔和資料檔案儲存在 SQL Server 預設路徑所指定的位置中， (這些路徑必須由 SQL Server 系統管理員) 設定為 [高級]。 資料檔案會儲存在預設的 SQL Server 資料檔案位置中，而記錄檔案則儲存在預設的 SQL Server 記錄檔案位置中。
    
4. 按一下 [確定]。
    
5. 在「建立資料庫」頁面上，按 [下一步]。
    
6. 在「資料庫建立完成」頁面上，按一下 [完成]。
