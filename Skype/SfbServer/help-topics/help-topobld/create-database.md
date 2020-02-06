---
title: 建立資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: '[拓撲建立器] 提供在 SQL Server store 上安裝資料庫的方法。 當您使用 [拓撲建立器] 來安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 群集上安裝所需的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或必須安裝 collocated 資料庫，則必須改為使用 Windows PowerShell 命令列介面和安裝 CsDatabase Cmdlet。'
ms.openlocfilehash: cd3bd6e24f0dc3ec21c5cfa8626d9696454855e7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820235"
---
# <a name="create-database"></a>建立資料庫
 
[拓撲建立器] 提供在 SQL Server store 上安裝資料庫的方法。 當您使用 [拓撲建立器] 來安裝資料庫時，應用程式會讀取拓撲中的資訊，然後在指定的 SQL Server 電腦或 SQL Server 群集上安裝所需的資料庫。 這是唯一可以使用拓撲產生器進行的資料庫安裝類型。 如果您需要在特定電腦上安裝特定資料庫，或必須安裝 collocated 資料庫，則必須改為使用 Windows PowerShell 命令列介面和[安裝 CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) Cmdlet。
  
### <a name="creating-a-database"></a>建立資料庫

1. 按一下商務用 Skype Server 2015 節點，然後按一下 [**安裝資料庫**]。
    
2. 在 [**安裝資料庫**] 對話方塊的 [**建立資料庫**] 頁面上，選取要建立新資料庫的 SQL Server store 的完整功能變數名稱（FQDN）。
    
3. 按一下 [進階]****。在 [選取資料庫檔案位置]**** 對話方塊中，選取下列其中一個選項：
    
   - **自動判斷資料庫檔案位置**。選取此選項時，拓撲產生器會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。
    
   - **使用 SQL Server 執行個體預設值**。 選取此選項時，不會使用內建的演算法選擇資料庫記錄與資料檔案的儲存位置。 相反地，記錄和資料檔案會儲存在 SQL Server 預設路徑所指定的位置（這些路徑必須由 SQL Server 系統管理員設定為高級）。 資料檔案會儲存在預設的 SQL Server 資料檔案位置中，而記錄檔案則儲存在預設的 SQL Server 記錄檔案位置中。
    
4. 按一下 [確定]****。
    
5. 在「建立資料庫」**** 頁面上，按 [下一步]****。
    
6. 在「資料庫建立完成」**** 頁面上，按一下 [完成]****。
    

