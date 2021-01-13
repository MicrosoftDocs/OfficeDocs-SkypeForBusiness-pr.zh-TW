---
title: 在商務用 Skype Server 中將封存資料庫新增至現有的部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b67df85-181d-45ca-ba48-bb74a439f242
description: 摘要：閱讀此主題以瞭解如何將封存資料庫新增至您的商務用 Skype Server 部署。
ms.openlocfilehash: f7642cb79f73ab519938ddcb680f8450347b943d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820673"
---
# <a name="add-archiving-databases-to-an-existing-deployment-in-skype-for-business-server"></a>在商務用 Skype Server 中將封存資料庫新增至現有的部署
 
**摘要：** 閱讀此主題以瞭解如何將封存資料庫新增至您的商務用 Skype Server 部署。
  
您必須先將封存納入拓撲中，才能設定部署來支援封存。 本主題中的資訊說明如何使用拓撲產生器來執行下列作業：
  
- 將封存資料庫新增至您的拓撲。
    
- 發行更新的拓撲，將封存資料庫新增至您的商務用 Skype Server 部署。
    
> [!NOTE]
> 如果您想要使用 Microsoft Exchange 整合將封存資料和檔案儲存在部署中的所有使用者的 Exchange 伺服器上，請勿指定封存 **SQL server 儲存區** ，或 **使用 SQL Server 儲存區鏡像** 資訊。
  
### <a name="add-an-archiving-database-to-your-topology"></a>將封存資料庫新增至您的拓撲

1. 在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或是具有同等使用者權限的帳戶) 。
    
2. 啟動拓撲產生器。
    
3. 在主控台樹中，流覽至您要部署封存的前端集區，然後按一下您要部署封存的前端集區名稱。
    
4. 在 [動作] 功能表上，按一下 [編輯屬性]。 
    
5. 在 **[編輯內容]** 對話方塊中，按一下 **[一般]**。
    
6. 向下捲動至 [封存]。
    
7. 選取 [封存] 核取方塊。
    
8. 在 **[封存 SQL Server 儲存區** ] 底下，執行下列其中一項操作：
    
   - 如要使用現有的 SQL Server 儲存區，在下拉式清單方塊中，按一下要使用的 SQL Server 儲存區名稱。 如果您的所有使用者都位於 Microsoft Exchange Server 2013 或以上，您可以封存 Exchange 中所有使用者的商務用 Skype 通訊。 在此情況下，您不需要設定 SQL Server 封存儲存區。
    
   - 若要指定新的 SQL Server 儲存區，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列動作：
    
   - 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 儲存區之伺服器的 FQDN。
    
   - 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
    
   - 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
9. 若要使用 SQL Server 儲存區鏡像，請選取 **[啟用 Sql Server 儲存區鏡像**]，然後執行下列動作：
    
   - 若要使用現有的 SQL Server 儲存區進行鏡像，請在 [封存 **SQL server 儲存區鏡像** ] 下拉式清單方塊中，按一下要用於鏡像的 SQL server 儲存區名稱。
    
   - 若要指定新的 SQL Server 儲存區以進行鏡像，請按一下 [ **新增**]，然後在 [ **定義新的 SQL server 儲存區** ] 對話方塊中，執行下列其中一項操作：
    
     a. 在 **[SQL SERVER FQDN**] 中，指定您要在其上建立新 sql server 儲存區之 sql SERVER 的 FQDN。
    
     b. 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要使用的執行個體。
    
     c. 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
   - 如果您啟用 SQL Server 鏡像，而且想要包含 SQL Server 鏡像見證 (第三個個別的 SQL Server 實例可以偵測主要 SQL Server 和鏡像實例的健康情況) ，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊，然後執行下列其中一項操作：
    
     a. 在 **[SQL SERVER FQDN**] 中，指定您要建立新 SQL Server 鏡像見證之伺服器的 FQDN。
    
     b. 按一下 **[預設執行個體]** 以使用預設執行個體，或者要指定不同的執行個體的話，按一下 **[具名執行個體]**，然後指定要作為鏡像見證的執行個體。
    
     c. 如果指定的 SQL Server 實例是以鏡像關聯，請選取 [ **此 sql 實例為鏡像關聯** ] 核取方塊，然後在 [ **鏡像埠號碼**] 中指定埠號碼。
    
10. 如要儲存設定，按一下 **[確定]**。
    
### <a name="publish-the-updated-topology-to-add-an-archiving-database-to-your-deployment"></a>發行更新的拓撲，將封存資料庫新增至您的部署

1. 在執行商務用 Skype 伺服器的電腦上，或安裝商務用 skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入 (或) 具有同等使用者權限的帳戶登入。
    
    > [!NOTE]
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，但發行拓撲（必須用來將伺服器新增至拓撲）。您必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶，且具有在您用於商務用 Skype server 檔案存放區之檔案共用上的「讀取」、「寫入」和「修改」) 的「完全控制」許可權，讓拓撲 (產生器可以設定所需的自由存取控制清單 (dacl) ，或具有對等權利的帳戶。 (
  
2. 使用拓撲產生器開啟您在上一節中建立的拓撲。
    
3. 在主控台樹中，以滑鼠右鍵按一下 [ **商務用 Skype 伺服器**]，然後按一下 [ **發行拓撲**]。
    
4. 在 **[發行拓樸]** 頁面上，按一下 **[下一步]**。
    
5. 在 **[建立資料庫]** 頁面上，確認已選取資料庫，然後按一下 **[下一步]**。 
    
    > [!NOTE]
    > 如果您未具備建立資料庫的適當權限，可以取消選取資料庫，讓具備適當權限的人能夠建立資料庫。 > 只有專用 SQL Server 上的資料庫可以使用拓撲產生器安裝。 與其他伺服器元件組合之 SQL server 上的資料庫必須透過在該電腦上執行本機安裝程式來安裝。 
  
6. 在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    
    > [!IMPORTANT]
    > 發行拓樸之後，您必須先為封存設定選項和原則，才能封存內容。 如需詳細資訊，請參閱設定商務用 [Skype 伺服器的封存選項](configure-archiving-options.md) 及 [設定商務用 skype 伺服器](configure-archiving-policies.md)的封存原則。 
  

