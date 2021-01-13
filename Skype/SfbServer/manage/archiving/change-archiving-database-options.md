---
title: 變更商務用 Skype Server 中的封存資料庫選項
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
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：瞭解如何變更商務用 Skype 伺服器的封存資料庫選項。
ms.openlocfilehash: 9a2b1056b6dd5d31c8b1dda658e219c345b28278
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817693"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>變更商務用 Skype Server 中的封存資料庫選項

**摘要：** 瞭解如何變更商務用 Skype 伺服器的封存資料庫選項。
  
如果您使用 SQL Server storage 部署封存，以封存任何使用者的儲存體，您可以進行下列資料庫儲存變更：
  
- 使用不同的 SQL Server 資料庫來封存儲存體。 這包括主要封存資料庫和您用來進行 SQL Server 鏡像的任何資料庫。
    
- 切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 伺服器上。 如果您的所有使用者都位於 Exchange 伺服器上，而您想要將 Microsoft Exchange storage 用於部署中的所有使用者，則應該從拓撲中移除 SQL Server 儲存區資料庫。 
    
若要進行這項變更，您必須執行拓撲產生器、進行變更，然後重新發佈拓撲。 除非您的商務用 Skype 使用者不是位於 Exchange 伺服器上，否則請勿指定封存 **Sql server 儲存區** 或 **啟用 SQL server 儲存區鏡像** 資訊。
  
## <a name="change-archiving-database-options"></a>變更封存資料庫選項

1. 在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或是具有同等使用者權限的帳戶) 。
    
    > [!NOTE]
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但若要發行拓撲（需要將元件新增至拓撲），則必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶。而且具有在您用於商務用 Skype Server 檔案存放區之檔案共用上的「完全控制」許可權 (（讀取、寫入及修改）) ，所以拓撲產生器可以設定所需的任意自由存取控制清單 (dacl) ，或具有 (對等權利的帳戶。
  
2. 啟動拓撲產生器。
    
3. 在主控台樹狀目錄中，瀏覽至部署封存的前端集區，然後按一下要變更資料庫選項的前端集區名稱。
    
4. 在 [動作] 功能表上，按一下 [編輯屬性]。 
    
5. 在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。
    
6. 向下捲動至 **[封存]**。
    
7. 在 **[封存]** 中，執行下列動作：
    
   - 如要變更至不同的現有 SQL Server 儲存區，在 [封存 SQL Server 儲存區] 的下拉式清單方塊中，執行下列動作：
    
   - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
    
   - 如要指定新的 SQL Server 儲存區，按一下 **[新增]**，然後在 **[定義新的 SQL Server 儲存區]** 對話方塊中，執行下列動作：
    
     - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。
    
     - 若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：
    
       - 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。
    
       - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
    
       - 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
   - 如要新增 SQL Server 儲存區作為鏡像，或者變更至不同的現有 SQL Server 儲存區作為 SQL Server 儲存區鏡像，則選取 **[啟用 SQL Server 儲存區鏡像]**，然後執行下列動作：
    
     - 若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。
    
     - 若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：
    
       a. 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。
    
       b. 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
    
       c. 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
   - 如果您啟用 SQL Server 鏡像，並且想要新增或變更 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 服務器的健康情況及鏡像實例) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：
    
      a. 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。
    
      b. 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
    
      c. 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
   - 若要切換至 Microsoft Exchange 整合，將封存資料和檔案儲存在 Exchange 伺服器上 (如果您部署中的所有使用者都位於 Exchange 伺服器) 上，請刪除封存資料庫的所有資訊。
    
     > [!IMPORTANT]
     > 如果您有任何商務用 Skype 使用者非位於 Exchange 伺服器上，請勿刪除 SQL Server 儲存區資訊。 
  
8. 如要儲存設定，按一下 **[確定]**。
    
    > [!IMPORTANT]
    > 在您發佈新的拓撲之前，您在拓撲產生器中所做的變更不會生效。 如需詳細資訊，請參閱 [在商務用 Skype Server 中新增封存資料庫至現有的部署](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用 Windows PowerShell 變更封存資料庫的位置

在大多數情況下，您不需要變更封存資料庫的位置，此資料庫會在您安裝封存伺服器時指定。 不過，如果發生硬體故障或其他問題，您可以使用 **CsArchivingServer** 指令程式將封存伺服器指向新的資料庫。
  
下列範例會變更 ArchivingServer： atl-cs-001.contoso.com 封存伺服器之封存資料庫的位置。 在此範例中，新的資料庫位於 ArchivingDatabase： atl-sql-001.contoso.com：
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


