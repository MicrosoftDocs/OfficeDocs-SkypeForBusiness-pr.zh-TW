---
title: 在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復。
ms.openlocfilehash: 5823d4aa9df744c8a7e0b133f7e4798ddcf712c8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392475"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復
 
**總結：** 瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 的高可用性和嚴重損壞修復。
  
本主題說明如何容錯移轉和容錯回復持久聊天伺服器。 閱讀本主題之前，請務必先閱讀[Plan for persistent chat server in 商務用 Skype Server 2015 的高可用性和嚴重](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)損壞修復，並[在商務用 Skype Server 2015 中設定 persistent chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。

> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
  
## <a name="fail-over-persistent-chat-server"></a>容錯移轉 Persistent Chat Server

Persistent Chat Server 的容錯移轉是設計為主要是手動處理常式。
  
容錯移轉程式的假設是在次要資料中心啟動並執行，但主要 Persistent Chat 資料庫所在的 Persistent Chat Server 服務完全無法使用，包括下列各項：
  
- Persistent Chat Server 主資料庫和 Persistent Chat Server 鏡像資料庫已停機。
    
- 商務用 Skype Server 前端伺服器已關機。
    
此程序主要有兩個基本步驟：
  
- 復原主要 Persistent Chat database (mgc) 。
    
- 建立新主要資料庫的鏡像。
    
Persistent Chat 規範資料庫 (mgccomp) 未進行容錯移轉。 此資料庫的內容僅為暫時性，且會在規範介面卡處理資料時被清除。 您的責任是 Persistent Chat Administrator，可正確管理配接器輸出以避免資料遺失。
  
若要容錯移轉 Persistent Chat Server：
  
1. 從 Persistent Chat Server 備份記錄傳送資料庫中移除記錄傳送。
    
   - 使用 SQL Server Management Studio，連接至 Persistent Chat Server backup mgc 資料庫所在的資料庫實例。
    
   - 開啟 Master 資料庫的查詢視窗。
    
   - 使用下列命令移除記錄傳送：
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 從備份共用複製所有未複製的備份檔案至備份伺服器的複製目的地資料夾。
    
3. 依序將所有未套用的交易記錄備份套用至次要資料庫。 如需詳細資訊，請參閱 how [to：將交易記錄備份 (Transact-SQL) ](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))。
    
4. 若要使備份 mgc 資料庫上線。請使用步驟 1b 中開啟的查詢視窗，執行下列動作：
    
   - 結束所有 mgc 資料庫的連線 (若有連線)：
    
   - **exec sp_who2** 來識別 mgc 資料庫的連線。
    
   - **殺 \<spid\>** 以結束這些連線。
    
   - 使資料庫上線：
    
   - **restore database mgc with recovery**。
    
5. 在商務用 Skype Server 管理命令介面中，使用 command **Set-CsPersistentChatState 身分識別 "服務： 001.litwareinc.com"-PoolState FailedOver** 以容錯移轉至 mgc 備份資料庫。 請務必將 Persistent Chat 集區的完整功能變數名稱取代為 atl-cs-001.litwareinc.com。
    
    現在 mgc 備份資料庫已是主要資料庫。
    
6. 在商務用 Skype Server 管理命令介面中，使用 **Install-CsMirrorDatabase** Cmdlet 為現在用作主資料庫的備份資料庫建立高可用性鏡像。 使用備份資料庫執行個體作為主要資料庫，而使用備份鏡像資料庫執行個體作為鏡像執行個體。 此鏡像並不是安裝程式期間，最初為主要資料庫設定的鏡像。
    
7. 設定 Persistent Chat Server active server。 從商務用 Skype Server 管理命令介面，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。
    
    > [!IMPORTANT]
    > 所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。 
  
    此時，從 Persistent Chat Server 主資料庫到 Persistent Chat Server backup 資料庫的容錯移轉已成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>容錯回復 Persistent Chat Server

此程式概述從持久聊天伺服器失敗復原所需的步驟，以及從主要資料中心重新建立作業。
  
在 Persistent Chat Server 失敗的情況下，主要資料中心會受到完全中斷，主要和鏡像資料庫將無法使用。 主要資料中心會容錯移轉至備份伺服器。
  
在備份主要資料中心，及重建伺服器後，下列程序會還原正常作業。 此程式假設主要資料中心已經從總中斷中復原，而且已使用拓撲產生器重新建立並重新安裝 mgc 資料庫和 mgccomp 資料庫。
  
此程式也會假設在容錯移轉期間未部署任何新的鏡像和備份伺服器，而且部署的唯一伺服器是備份伺服器及其鏡像伺服器，如先前容錯移轉 Persistent Chat Server 所定義。
  
災難導致主要伺服去失敗，作業轉移至備份伺服器，因為災難發生前設定就存在，設計這些步驟就是用來還原設定。
  
1. 使用來自商務用 Skype Server 管理命令介面的 **Set-CsPersistentChatActiveServer** Cmdlet，清除 Persistent Chat Server 作用中伺服器清單中的所有伺服器。 這會在回切期間停止所有持久聊天伺服器連線至 mgc 資料庫和 mgccomp 資料庫。
    
    > [!IMPORTANT]
    > 次要 Persistent Chat server 後端伺服器上的 SQL Server 代理程式應以特權帳戶執行。 具體來說，帳戶必須包括： 
  
   - 對備份所在位置之網路共用的讀取存取權。
    
   - 對備份複製目的位置之特定本機目錄的寫入存取權。
    
2. 停用備份 MGC 資料庫上的鏡像：
    
   - 使用 SQL Server Management Studio 連接至備份 mgc 實例。
    
   - 用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[鏡像]**。
    
   - 按一下 **[移除鏡像]**。
    
   - 按一下 **[確定]**。
    
   - 使用 Mgccomp 資料庫執行相同步驟。
    
3. 備份 MGC 資料庫以便將其還原至新的主要資料庫：
    
   - 使用 SQL Server Management Studio 連接至備份 mgc 實例。
    
   - 用滑鼠右鍵按一下 MGC 資料庫，指向 **[工作]**，然後按一下 **[備份]**。**[備份資料庫]** 對話方塊隨即顯示。
    
   - 在 **[備份類型]** 中選取 **[完整]**。
    
   - 針對 **[備份元件]** 按一下 **[資料庫]**。
    
   - 接受 **[名稱]** 中建議的預設備份組名稱，或為備份組輸入不同名稱。
    
   -  *\<Optional\>*  在 [ **描述**] 中，輸入備份組的描述。
    
   - 從目的地清單移除預設備份位置。
    
   - 使用您為記錄傳送建立的共用位置路徑來將檔案新增至清單。主要資料庫和備份資料庫均可使用此路徑。
    
   - 按一下 **[確定]** 以關閉對話方塊並開始備份程序。
    
4. 使用先前步驟中建立的備份資料庫來還原主要資料庫。
    
   - 使用 SQL Server Management Studio 連接至主要 mgc 實例。
    
   - 以滑鼠右鍵按一下 MGC 資料庫，依序指向 **[工作]** 和 **[還原]**，然後按一下 **[資料庫]**。**[還原資料庫]** 對話方塊隨即顯示。
    
   - 選取 **[來源裝置]**。
    
   - 按一下開啟 **[指定備份]** 對話方塊的 [瀏覽] 按鈕。在 **[備份媒體]** 中，選取 **[檔案]**。按一下 **[新增]**，選取您在步驟 3 中建立的備份檔案，然後按一下 **[確定]**。
    
   - 在 **[選取要還原的備份組]** 中選取備份。
    
   - 在 **[選取頁面]** 窗格中按一下 **[選項]**。
    
   - 在 **[還原選項]** 中選取 **[覆寫現有資料庫]**。
    
   - 在 **[復原狀態]** 中選取 **[讓資料庫保持備妥可用]**。
    
   - 按一下 **[確定]** 開始復原程序。
    
5. 為主資料庫設定 SQL Server 記錄傳送。 請遵循在[商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復中](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)的程式，以建立主要 mgc 資料庫的記錄傳送。
    
6. 設定 Persistent Chat Server active server。 從商務用 Skype Server 管理命令介面，使用 **Set-CsPersistentChatActiveServer** Cmdlet 來設定作用中的伺服器清單。
    
    > [!IMPORTANT]
    > 所有作用中的伺服器必須位於與新主要資料庫相同的資料中心，或位於具有低延遲/高頻寬資料庫連線的資料中心內。 
  
若要將集區還原至正常狀態，請執行下列 Windows PowerShell 命令：
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

如需詳細資訊，請參閱 [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) Cmdlet 的 [說明] 主題。
