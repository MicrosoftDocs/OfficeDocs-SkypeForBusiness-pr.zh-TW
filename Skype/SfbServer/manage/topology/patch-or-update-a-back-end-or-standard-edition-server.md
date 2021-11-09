---
title: 在商務用 Skype Server 中修補或更新後端伺服器或 Standard Edition 伺服器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要：瞭解如何在商務用 Skype Server 中的後端伺服器上安裝更新或修補程式。
ms.openlocfilehash: 55d81e97712abe51544a854bf175348526e9f29c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858210"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>在商務用 Skype Server 中修補或更新後端伺服器或 Standard Edition 伺服器
 
**摘要：** 瞭解如何在商務用 Skype Server 中的後端伺服器上安裝更新或修補程式。
  
本主題說明如何在 Enterprise Edition 後端伺服器或 Standard Edition 伺服器上安裝更新。
  
如果後端伺服器停機至少30分鐘，則使用者可能會進入復原模式。 當升級完成且後端伺服器重新連接至集區中的前端伺服器後，使用者會傳回完整功能。 如果升級所需的時間少於30分鐘，使用者將不會受到影響。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新後端伺服器或 Standard Edition 伺服器

1. 以 CsAdministrator 角色成員身分登入您要升級的伺服器。
    
2. 下載更新，並將其解壓縮至本機硬碟。
    
3. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
4. 停止商務用 Skype Server 服務。 在命令列中輸入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. 停止全球資訊網服務。在命令列中輸入：
    
    ```PowerShell
    net stop w3svc
   ```

6. 關閉所有商務用 Skype Server 管理命令介面視窗。
    
7. 安裝更新。
    
8. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
9. 停用商務用 Skype Server 服務，以 (GAC) 集區中捕捉全域組件快取。 在命令列中輸入：
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. 重新啟動全球資訊網服務。在命令列中輸入：
    
    ```PowerShell
    net start w3svc
    ```

11. 執行下列其中一項，套用對 SQL Server 資料庫所做的變更：
    
    - 如果這是 Enterprise Edition 後端伺服器，且此伺服器上沒有組合資料庫（例如封存或監控資料庫），請在命令列輸入下列命令：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果這是 Enterprise Edition 後端伺服器，且此伺服器上有組合資料庫，請在命令列輸入下列命令：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果這是 Standard Edition 伺服器，請在命令列輸入下列命令：
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
