---
title: 在商務用 Skype Server 中新增封存資料庫至現有的部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: '摘要: 請閱讀本主題, 以瞭解如何將封存資料庫新增到您的商務用 Skype Server 部署。'
ms.openlocfilehash: b7d429206e003042922b9b9cae6de420fdf517bb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234580"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>在商務用 Skype Server 中新增封存資料庫至現有的部署
 
**摘要:** 請閱讀本主題, 以瞭解如何將封存資料庫新增到您的商務用 Skype Server 部署。
  
您必須先將存檔納入拓撲中, 才能設定您的部署支援封存。 本主題中的資訊說明如何使用拓撲產生器進行下列作業:
  
- 新增封存資料庫至您的拓撲。
    
- 發佈更新的拓撲, 以將封存資料庫新增到您的商務用 Skype Server 部署。
    
> [!NOTE]
> 如果您想要使用 Microsoft Exchange 整合來在 Exchange 伺服器上為您的部署中的所有使用者儲存存檔資料和檔案, 請勿指定 **[封存 Sql server store** ] 或 **[使用 SQL Server store 鏡像**資訊]。
  
### <a name="add-an-archiving-database-to-your-topology"></a>在拓撲中新增封存資料庫

1. 在執行商務用 Skype Server 的電腦上, 或安裝 [商務用 Skype Server] 管理工具的電腦上, 使用屬於 [本機使用者] 群組成員的帳戶登入 (或是擁有同等使用者權限的帳戶)。
    
2. 啟動拓撲建立器。
    
3. 在主控台樹中, 流覽至您要在其中部署封存的 [前端] 池, 然後按一下您要部署封存的 [前端] 池名稱。
    
4. 在 [**動作**] 功能表中, 按一下 [**編輯屬性**]。 
    
5. 在 [**編輯屬性**] 對話方塊中, 按一下 **[一般**]。
    
6. 向下滾動**** 至 [封存]。
    
7. 選取 [**存檔**] 核取方塊。
    
8. 在 **[封存 SQL Server store** ] 底下, 執行下列其中一項操作:
    
   - 若要使用現有的 SQL Server store, 請在下拉式清單方塊中, 按一下您要使用之 SQL Server store 的名稱。 如果您的所有使用者都是以 Microsoft Exchange Server 2013 或更高版本為宿主, 您可以將 Exchange 中所有使用者的商務用 Skype 通訊封存。 在這種情況下, 您不需要設定 SQL Server 封存存放區。
    
   - 若要指定新的 SQL Server 存放區, 請按一下 [**新增**], 然後在 [**定義新的 sql server store** ] 對話方塊中, 執行下列動作:
    
   - 在 **[SQL SERVER FQDN**] 中, 指定您要在其上建立新的 SQL Server 存放區之伺服器的 FQDN。
    
   - 按一下 [**預設實例**] 以使用預設實例, 或者, 若要指定不同的實例, 請按一下 [**命名實例**], 然後指定您要使用的實例。
    
   - 如果指定的 SQL Server 實例是在鏡像關聯中, 請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊, 然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
9. 如果您想要使用 SQL Server store 鏡像, 請選取 **[啟用 Sql Server store 鏡像**], 然後執行下列動作:
    
   - 若要使用現有的 SQL Server store 進行鏡像, 請在 [封存**Sql server store** ] 下拉式清單方塊中, 按一下您要用來進行鏡像的 SQL Server store 名稱。
    
   - 若要指定新的 SQL Server 存放區以進行鏡像, 請按一下 [**新增**], 然後在 [**定義新的 sql server store** ] 對話方塊中, 執行下列其中一項操作:
    
     是. 在 **[SQL SERVER FQDN**] 中, 指定您要在其上建立新的 sql server 存放區之 sql SERVER 的 FQDN。
    
     乙. 按一下 [**預設實例**] 以使用預設實例, 或者, 若要指定不同的實例, 請按一下 [**命名實例**], 然後指定您要使用的實例。
    
     c-clip. 如果指定的 SQL Server 實例是在鏡像關聯中, 請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊, 然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
   - 如果您啟用 SQL Server 鏡像, 且想要包含 SQL Server 鏡像見證 (第三個獨立的 SQL Server 實例, 可偵測到主要 SQL Server 和鏡像實例的健康情況), 請選取 [**使用 SQL Server 鏡像見證來啟用自動][容錯移轉**] 核取方塊, 然後執行下列其中一項操作:
    
     是. 在 **[SQL SERVER FQDN**] 中, 指定您要在其上建立新的 SQL Server 鏡像見證的伺服器 FQDN。
    
     乙. 按一下 [**預設實例**] 以使用預設實例, 或按一下 [指定**實例**], 然後指定您要用於鏡像見證的實例。
    
     c-clip. 如果指定的 SQL Server 實例是在鏡像關聯中, 請選取 [**此 sql 實例是使用鏡像關聯**] 核取方塊, 然後在 [**鏡像埠號碼**] 中指定埠號碼。
    
10. 若要儲存配置, 請按一下 **[確定]**。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>發佈已更新的拓撲, 以將封存資料庫新增到您的部署

1. 在執行商務用 Skype Server 的電腦上, 或已安裝商務用 Skype Server 系統管理工具的電腦上, 請使用屬於 [本機使用者] 群組成員的帳戶登入 (或是擁有同等使用者權利的帳戶)。
    
    > [!NOTE]
    > 您可以使用屬於 [本機使用者] 群組成員的帳戶來定義拓朴, 但若要發佈拓撲 (需要將伺服器新增至拓撲結構), 您必須使用**網域系統管理員**群組和 RTCUniversalServer 成員的帳戶。 **系統管理員**群組, 且在您針對商務用 Skype Server 檔存放區使用的檔案共用上擁有完全控制許可權 (讀取、寫入及修改), 讓拓撲建立器可以設定必要的隨機存取控制清單 (dacl), 或具有同等權利的帳戶。
  
2. 使用拓撲建立器開啟您在前一節所建立的拓撲。
    
3. 在主控台樹中, 以滑鼠右鍵按一下 [**商務用 Skype Server**], 然後按一下 [**發佈拓撲**]。
    
4. 在 [**發佈拓撲**] 頁面上, 按一下 **[下一步]**。
    
5. 在 [**建立資料庫**] 頁面上, 確認已選取資料庫, 然後按一下 **[下一步]**。 
    
    > [!NOTE]
    > 如果您沒有建立資料庫的適當許可權, 您可以取消選取資料庫, 且具有適當許可權的人員可以建立資料庫。 > 只有專用 SQL Server 上的資料庫才能使用拓撲建立器進行安裝。 與其他伺服器元件 collocated 之 SQL server 上的資料庫, 必須透過在該電腦上執行本機安裝程式來安裝。 
  
6. 在 [**發佈嚮導完成]** 頁面上, 確認拓撲已順利發佈, 然後按一下 **[完成]**。
    
    > [!IMPORTANT]
    > 發佈拓朴之後, 您必須先設定用於封存的選項和原則, 才能存檔任何內容。 如需詳細資訊, 請參閱[設定商務用 Skype server](configure-archiving-options.md)的封存選項, 以及[設定商務用 skype server 的存檔原則](configure-archiving-policies.md)。 
  

