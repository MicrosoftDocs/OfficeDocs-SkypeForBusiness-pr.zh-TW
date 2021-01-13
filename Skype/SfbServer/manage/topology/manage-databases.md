---
title: 在商務用 Skype Server 中管理具有 AlwaysOn 可用性群組的資料庫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 摘要：瞭解如何將更多商務用 Skype Server 資料庫新增至現有的 AlwaysOn 可用性群組，以及在修補或升級後端伺服器（屬於商務用 Skype Server 中的 AlwaysOn 可用性群組一部分）之後，瞭解必要的額外步驟。
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826363"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>在商務用 Skype Server 中管理具有 AlwaysOn 可用性群組的資料庫

使用本文中的步驟，將更多商務用 Skype 伺服器資料庫新增至現有的 AlwaysOn 可用性群組中的商務用 Skype Server 中，並在修補或升級後端伺服器（屬於商務用 Skype Server 中的 AlwaysOn 可用性群組一部分）之後，查看必要的額外步驟。

## <a name="add-databases-to-an-alwayson-availability-group"></a>將資料庫新增至 AlwaysOn 可用性群組 

1. 開啟 SQL Server Management Studio，然後流覽至 [AlwaysOn 可用性] 群組。 將其容錯移轉至主要複本。
    
2. 在 [拓撲產生器] 中，將 [AlwaysOn 可用性] 群組的 SQL Server FQDN 設定為該群組主要節點的 FQDN。
    
   - 開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。
    
   - 展開 [商務用 Skype 伺服器]，展開您的拓撲，然後展開 **[SQL Server 儲存區**]。 以滑鼠右鍵按一下新 AlwaysOn 可用性群組的 SQL 存放區，然後按一下 [ **編輯屬性**]。
    
   - 在頁面底部的 [ **SQL SERVER FQDN** ] 方塊中，輸入 AlwaysOn 可用性群組之主要節點的 FQDN。
    
3. 發行拓撲。 從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。 然後在 [確認] 頁面中按 **[下一步]**。
    
4. 使用 SQL Server Management Studio 將新資料庫新增至 AlwaysOn 可用性群組。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>在 AlwaysOn 可用性群組中修補或更新 SQL Server

在修補屬於 AlwaysOn 可用性群組一部分的後端伺服器之後，您必須重新發佈拓撲。

1. 在商務用 Skype 伺服器或伺服器上安裝更新。
    
2. 在商務用 Skype 管理命令介面中執行下列 PowerShell 命令 (以適當專屬許可權將變更套用至 SQL AlwaysOn 資料庫的帳戶進行登錄) 如下所示：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中 [sqlpool.contoso.com] 會以 AlwaysOn 可用性群組的完整功能變數名稱 (FQDN) 取代。
