---
title: 在商務用 Skype Server 中修補或更新後端伺服器或標準版伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: '摘要: 瞭解如何在商務用 Skype Server 的後端伺服器上安裝更新或修補程式。'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187087"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>在商務用 Skype Server 中修補或更新後端伺服器或標準版伺服器
 
**摘要:** 瞭解如何在商務用 Skype Server 的後端伺服器上安裝更新或修補程式。
  
本主題說明如何在企業版後端伺服器或標準版伺服器上安裝更新。
  
如果後端伺服器在您升級時至少有30分鐘的時間, 使用者可能會進入復原模式。 完成升級後, 後端伺服器再次與池中的前端伺服器連線之後, 使用者就會回到完整功能。 如果升級所需的時間少於30分鐘, 使用者將不會受到影響。
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>更新後端伺服器或標準版伺服器

1. 以 CsAdministrator 角色成員的身分登入您要升級的伺服器。
    
2. 下載更新並將它解壓縮到本機硬碟。
    
3. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype**], 然後按一下 [商務用**skype Server 管理命令**介面]。
    
4. 停止商務用 Skype Server 服務。 在命令列中, 輸入:
    
    ```
    Stop-CsWindowsService
    ```

5. 停止萬維網服務。 在命令列中, 輸入:
    
    ```
    net stop w3svc
   ```

6. 關閉所有商務用 Skype Server Management Shell 視窗。
    
7. 安裝更新。
    
8. 啟動商務用 Skype Server 管理命令介面: 請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**], 然後按一下 [**商務用 skype server 管理命令**介面]。
    
9. 再次停止商務用 Skype Server services, 以捕捉通用群組件緩存 (GAC)-d 元件。 在命令列中, 輸入:
    
    ```
    Stop-CsWindowsService
    ```

10. 重新開機萬維網服務。 在命令列中, 輸入:
    
    ```
    net start w3svc
    ```

11. 執行下列其中一項操作, 以套用對 SQL Server 資料庫所做的變更:
    
    - 如果這是企業版後端伺服器, 且此伺服器上沒有 collocated 資料庫 (例如 [封存] 或 [監視資料庫]), 請在命令列中輸入下列內容:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - 如果這是企業版後端伺服器, 且此伺服器上有 collocated 資料庫, 請在命令列中輸入下列內容:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - 如果這是標準版 server, 請在命令列輸入以下命令:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
