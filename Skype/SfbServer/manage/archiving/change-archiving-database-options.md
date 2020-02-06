---
title: 在商務用 Skype Server 中變更封存資料庫選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dbebaa0a-f3a2-4dbd-b64e-07a62370f899
description: 摘要：瞭解如何變更商務用 Skype Server 的存檔資料庫選項。
ms.openlocfilehash: c489117894eca69141ac07860c45aa07eb5916ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818975"
---
# <a name="change-archiving-database-options-in-skype-for-business-server"></a>在商務用 Skype Server 中變更封存資料庫選項

**摘要：** 瞭解如何變更商務用 Skype Server 的存檔資料庫選項。
  
如果您使用 SQL Server storage 部署歸檔來儲存任何使用者的儲存空間，您可以變更下列資料庫儲存空間：
  
- 使用不同的 SQL Server 資料庫來存檔儲存空間。 這包括主要的歸檔資料庫，以及您用於 SQL Server 鏡像的任何資料庫。
    
- 切換至 Microsoft Exchange 整合，以儲存 Exchange 伺服器上的封存資料和檔案。 如果您的所有使用者都是駐留在 Exchange 伺服器上，而您想要在部署中的所有使用者都使用 Microsoft Exchange 儲存空間，您應該從拓撲中移除 SQL Server store 資料庫。 
    
若要進行其中一個變更，您必須執行拓撲建立器，進行變更，然後再次發佈拓撲。 除非您有不在 Exchange 伺服器上的商務用 Skype 使用者，否則請勿指定 **[封存 Sql server store** ] 或 **[啟用 sql server store 鏡像**資訊]。
  
## <a name="change-archiving-database-options"></a>變更封存資料庫選項

1. 在執行商務用 Skype Server 的電腦上，或安裝 [商務用 Skype Server] 管理工具的電腦上，使用屬於 [本機使用者] 群組成員的帳戶登入（或是擁有同等使用者權限的帳戶）。
    
    > [!NOTE]
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴，但若要發佈拓撲，必須將元件新增到拓撲中。您必須使用的帳戶是**Domain Admins**群組和**RTCUniversalServerAdmins**群組的成員，且在您用於商務用 Skype Server 檔存放區的檔案共用上擁有完全控制許可權（也就是讀取、寫入及修改），讓拓撲建立器可以設定必要的隨機存取控制清單（Dacl）或具有同等許可權的帳戶。
  
2. 啟動拓撲建立器。
    
3. 在主控台樹中，流覽至您已部署封存的 [前端] 池，然後按一下您要變更資料庫選項的前端池名稱。
    
4. 在 [**動作**] 功能表中，按一下 [**編輯屬性**]。 
    
5. 在 [**編輯屬性**] 對話方塊中，按一下 **[一般**]。
    
6. **向下滾動至 [** 封存]。
    
7. 在 [**存檔**] 中，執行下列動作：
    
   - 若要變更為不同的現有 SQL Server store，請在 [封存**Sql server store**] 下的下拉式清單方塊中，執行下列動作：
    
   - 若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。
    
   - 若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：
    
     - 若要使用現有的 SQL Server store，請在下拉式清單方塊中，按一下您要使用之 SQL Server store 的名稱。
    
     - 若要指定新的 SQL Server 存放區，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列動作：
    
       - 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。
    
       - 按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。
    
       - 如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
   - 若要新增 SQL Server store 以進行鏡像或變更為其他現有的 sql server store for SQL server store 鏡像，請選取 [**啟用 SQL Server store 鏡像**]，然後執行下列動作：
    
     - 若要使用現有的 SQL Server store 進行鏡像，請在 [封存**Sql server store** ] 下拉式清單方塊中，按一下您要用來進行鏡像的 SQL Server store 名稱。
    
     - 若要指定新的 SQL Server 存放區以進行鏡像，請按一下 [**新增**]，然後在 [**定義新的 sql server store** ] 對話方塊中，執行下列其中一項操作：
    
       是. 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。
    
       乙. 按一下 [**預設實例**] 以使用預設實例，或者，若要指定不同的實例，請按一下 [**命名實例**]，然後指定您要使用的實例。
    
       c-clip. 如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
   - 如果您啟用 SQL Server 鏡像，並想要新增或變更 SQL Server 鏡像見證（第三個是可偵測主要 SQL Server 服務器與鏡像實例之健康情況的第三個 SQL Server 實例），請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊，然後執行下列其中一項操作：
    
      是. 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。
    
      乙. 按一下 [**預設實例**] 以使用預設實例，或按一下 [指定**實例**]，然後指定您要用於鏡像見證的實例。
    
      c-clip. 如果指定的 SQL Server 實例是在鏡像關聯中，請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊，然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
   - 若要切換至 Microsoft Exchange 整合，以將封存資料和檔案儲存在 Exchange 伺服器上（如果您部署中的所有使用者都駐留在您的 Exchange 伺服器上），請刪除所有儲存資料庫的資訊。
    
     > [!IMPORTANT]
     > 如果您有任何不是駐留在 Exchange 伺服器上的商務用 Skype 使用者，請勿刪除 SQL Server store 資訊。 
  
8. 若要儲存配置，請按一下 **[確定]**。
    
    > [!IMPORTANT]
    > 您在拓撲建立器中所做的變更不會生效，除非您發佈新的拓撲。 如需詳細資訊，請參閱[在商務用 Skype Server 中新增封存資料庫至現有的部署](../../deploy/deploy-archiving/add-archiving-databases.md)。 
  
## <a name="change-the-location-of-the-archiving-database-by-using-windows-powershell"></a>使用 Windows PowerShell 變更封存資料庫的位置

在大多數情況下，您不需要變更封存資料庫的位置，這是在您安裝 [封存伺服器] 時指定的。 不過，如果發生硬體故障或其他問題，您可以使用**CsArchivingServer** Cmdlet，將存檔伺服器指向新的資料庫。
  
下列範例會變更 ArchivingServer 的存檔資料庫的位置： atl-cs-001.contoso.com 封存伺服器。 在這個範例中，新的資料庫位於 ArchivingDatabase： atl-sql-001.contoso.com：
  
```PowerShell
Set-CsArchivingServer -Identity "ArchivingServer:atl-cs-001.contoso.com" -ArchivingDatabase "ArchivingDatabase:atl-sql-001.contoso.com"
```


