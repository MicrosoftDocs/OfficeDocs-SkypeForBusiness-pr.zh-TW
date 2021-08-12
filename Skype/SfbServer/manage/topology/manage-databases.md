---
title: 使用商務用 Skype Server 管理 AlwaysOn 可用性群組的資料庫
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
description: 摘要：瞭解如何將更多商務用 Skype Server 資料庫新增至現有 AlwaysOn 可用性群組，以及在您修補或升級屬於商務用 Skype Server AlwaysOn 可用性群組一部分的後端伺服器之後，深入瞭解必要的額外步驟。
ms.openlocfilehash: 705fc69d1c29807a0f32276a28268f2da932056d38e306db45b8c68e81f9a11b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314449"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>使用商務用 Skype Server 管理 AlwaysOn 可用性群組的資料庫

使用本文中的步驟，將更多商務用 Skype Server 資料庫新增至商務用 Skype Server 中現有的 AlwaysOn 可用性群組，並在修補或升級後端伺服器（屬於商務用 Skype Server 中 AlwaysOn 可用性群組的一部分）中，找出必要的額外步驟。

## <a name="add-databases-to-an-alwayson-availability-group"></a>將資料庫新增至 AlwaysOn 可用性群組 

1. 開啟 SQL Server Management Studio，然後流覽至 AlwaysOn 可用性群組。 將其容錯移轉至主要複本。
    
2. 在 [拓撲產生器] 中，將 AlwaysOn 可用性群組的 SQL Server fqdn 設定為該群組的主要節點的 fqdn。
    
   - 開啟拓撲產生器，選取 [ **從現有的部署下載拓撲**]，然後按一下 **[確定]**。
    
   - 展開商務用 Skype Server，展開您的拓撲，然後展開 **SQL Server 儲存區**。 以滑鼠右鍵按一下新 AlwaysOn 可用性群組的 SQL 儲存區，然後按一下 [**編輯屬性**]。
    
   - 在頁面底部的 [ **SQL Server FQDN** ] 方塊中，輸入 AlwaysOn 可用性群組之主要節點的 FQDN。
    
3. 發行拓撲。 從 [ **動作** ] 功能表中，按一下 [ **拓撲** ]，然後再 **發佈**。 然後在 [確認] 頁面中按 **[下一步]**。
    
4. 使用 SQL Server Management Studio 將新資料庫新增至 AlwaysOn 可用性群組。
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>在 AlwaysOn 可用性群組中修補或更新 SQL Server

在修補屬於 AlwaysOn 可用性群組一部分的後端伺服器之後，您必須重新發佈拓撲。

1. 在商務用 Skype 伺服器或伺服器上安裝更新。
    
2. 在商務用 Skype 管理命令介面中執行下列 PowerShell 命令 (使用適當專屬許可權將變更套用至 SQL AlwaysOn 資料庫的帳戶來登入) 如下所示：
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    其中 [sqlpool.contoso.com] 會以 AlwaysOn 可用性群組的完整功能變數名稱 (FQDN) 取代。
