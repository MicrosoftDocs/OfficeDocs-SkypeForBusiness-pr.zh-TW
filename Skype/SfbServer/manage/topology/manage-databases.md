---
title: 在商務用 Skype Server 中使用 AlwaysOn 可用性群組管理資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '摘要: 瞭解如何將更多商務用 Skype Server 資料庫新增至現有的 AlwaysOn 可用性群組, 並瞭解在 Skype 中修補或升級作為 AlwaysOn 可用性群組一部分的後端伺服器之後所需的其他步驟。商務伺服器。'
ms.openlocfilehash: c6d8877448a68aa2331f3c290170418f6dca08ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187105"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>在商務用 Skype Server 中使用 AlwaysOn 可用性群組管理資料庫

使用本文中的步驟, 在商務用 Skype Server 的現有 AlwaysOn 可用性群組中新增更多商務用 Skype Server 資料庫, 並在您修補或升級屬於 AlwaysOn 的後端伺服器之後, 找出必要的額外步驟商務用 Skype Server 中的 [可用性] 群組。

## <a name="add-databases-to-an-alwayson-availability-group"></a>新增資料庫至 AlwaysOn 可用性群組 

1. 開啟 SQL Server Management Studio, 然後流覽至 [AlwaysOn 可用性] 群組。 將它容錯移轉到主要複本。
    
2. 在 [拓撲建立器] 中, 將 [AlwaysOn 可用性] 群組的 SQL Server FQDN 設定為該組主要節點的 FQDN。
    
   - 開啟拓撲建立器, 選取 [**從現有部署下載拓撲**], 然後按一下 **[確定]**。
    
   - 展開 [商務用 Skype 伺服器]、展開您的拓撲, 然後展開 **[SQL Server 存放區**]。 以滑鼠右鍵按一下新 [AlwaysOn 可用性] 群組的 SQL 存放區, 然後按一下 [**編輯屬性**]。
    
   - 在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中, 輸入 [AlwaysOn 可用性] 群組主要節點的 FQDN。
    
3. 發佈拓撲。 從 [**動作**] 功能表按一下 [**拓撲**], 然後按一下 [**發佈**]。 然後在確認頁面中, 按一下 **[下一步]**。
    
4. 使用 SQL Server Management Studio 將新資料庫新增至 [AlwaysOn 可用性] 群組。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>在 AlwaysOn 可用性群組中修補或更新 SQL Server

在針對屬於 AlwaysOn 可用性群組的後端伺服器進行修補之後, 您必須重新發佈拓撲。

1. 在商務用 Skype 伺服器或伺服器上安裝更新。
    
2. 在商務用 Skype 管理 Shell 中執行下列 PowerShell 命令 (以適當 permissioned 的帳戶登入, 以將變更套用至 SQL AlwaysOn 資料庫), 如下所示:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中 [sqlpool.contoso.com] 會以您的 AlwaysOn 可用性群組的完整功能變數名稱 (FQDN) 取代。
