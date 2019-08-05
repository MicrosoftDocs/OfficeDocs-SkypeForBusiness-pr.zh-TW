---
title: 管理常設聊天室伺服器的高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器的高可用性和災害復原。'
ms.openlocfilehash: ff30bcdd99a4c92bd8fbd8f0a5c4bcedd8aa63b0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194065"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>管理常設聊天室伺服器的高可用性和災害復原
 
**摘要:** 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器的高可用性和災害復原。
  
本主題說明如何進行容錯移轉及自動容錯回復持久聊天伺服器。 在閱讀本主題之前, 請務必閱讀適用于[商務用 Skype server 2015 中持續性聊天伺服器的高可用性和災難復原方案](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md), 以及[在 Skype 中設定持續聊天伺服器的高可用性與災難復原商務伺服器 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 
  
## <a name="fail-over-persistent-chat-server"></a>永久聊天伺服器容錯移轉

持續性聊天伺服器的容錯移轉主要是手動程式設計。
  
容錯移轉程式的假設是次要資料中心已啟動且正在執行, 但主要持久聊天資料庫所在的持久聊天伺服器服務完全無法使用, 包括下列各項:
  
- 持續聊天伺服器主資料庫和持續聊天伺服器鏡像資料庫已關閉。
    
- 商務用 Skype Server 前端伺服器已關閉。
    
此程式是以兩個基本步驟為基礎:
  
- 復原主要持久聊天資料庫 (mgc)。
    
- 為新的主資料庫建立鏡像。
    
永久聊天規範資料庫 (mgccomp) 未進行容錯移轉。 此資料庫的內容是暫時性的, 而且會在合規性配接器處理資料時清除。 您的責任是永久聊天管理員, 正確管理配接器輸出以避免資料遺失。
  
若要容錯移轉持久聊天伺服器:
  
1. 從持續聊天伺服器備份記錄傳送資料庫中移除記錄傳送。
    
   - 使用 SQL Server Management Studio, 連線到持久聊天伺服器備份 mgc 資料庫所在的資料庫實例。
    
   - 開啟 [查詢] 視窗至 [主資料庫]。
    
   - 使用下列命令來刪除記錄傳送:
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 將備份共用中的任何 uncopied 備份檔案複製到備份伺服器的 [複製目的地] 資料夾。
    
3. 將任何未套用的事務記錄備份以順序套用到次要資料庫。 如需詳細資訊, 請參閱[如何: 套用事務記錄備份 (transact-sql)](https://go.microsoft.com/fwlink/p/?linkid=247428)。
    
4. 讓備份 mgc 資料庫在線上。 使用在步驟1b 中開啟的 [查詢] 視窗, 執行下列動作:
    
   - 結束所有 mgc 資料庫連線 (如果有的話):
    
   - **exec sp_who2** , 以找出 mgc 資料庫的連線。
    
   - **kill \<spid\> **以結束這些連線。
    
   - 讓資料庫處於線上狀態:
    
   - **使用恢復來還原資料庫 mgc**。
    
5. 在商務用 Skype Server Management 命令介面中, 使用命令**CsPersistentChatState 身分識別 "服務: atl-cs-001.litwareinc.com"-PoolState FailedOver**容錯移轉至 mgc 備份資料庫。 請務必以 atl-cs-001.litwareinc.com 的持久聊天池來取代完整的功能變數名稱。
    
    Mgc 備份資料庫現在是作為主要資料庫。
    
6. 在商務用 Skype Server Management 命令介面中, 使用**CsMirrorDatabase** Cmdlet 來為現在作為主要資料庫的備份資料庫建立高可用性鏡像。 使用備份資料庫實例作為主要資料庫, 將備份鏡像資料庫實例做為鏡像實例。 這與在安裝期間最初為主要資料庫設定的同一個鏡像。
    
7. 設定持續聊天伺服器的使用中伺服器。 從商務用 Skype Server Management Shell, 使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。
    
    > [!IMPORTANT]
    > 所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內, 或是在具有低延遲/高頻寬連接的資料中心中。 
  
    此時, 來自持久聊天伺服器主要資料庫的容錯移轉至持續聊天伺服器備份資料庫成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>容錯回復持久聊天伺服器

此程式概述從持續聊天伺服器失敗復原所需的步驟, 以及從主要資料中心重新建立作業。
  
在持續聊天伺服器發生故障期間, 主要資料中心會受到完全停機, 且主要和鏡像資料庫無法使用。 主要資料中心會容錯移轉至備份伺服器。
  
下列程式會在主要資料中心重新開機後還原正常作業, 且已重建伺服器。 此程式假設主要資料中心已從總停機中復原, 且 mgc 資料庫和 mgccomp 資料庫已使用拓撲產生器重建並重新安裝。
  
此程式也假設在容錯移轉期間, 沒有部署新的鏡像與備份伺服器, 而且部署的伺服器是備份伺服器及其鏡像伺服器 (在先前的 [容錯移轉前聊天伺服器] 中定義)。
  
這些步驟的設計目的是要在災難發生之前, 復原配置, 從而將主要伺服器的容錯移轉到備份伺服器。
  
1. 從商務用 Skype Server Management Shell 中使用**CsPersistentChatActiveServer** Cmdlet, 以清除永久聊天伺服器作用中伺服器清單中的所有伺服器。 這會在回切期間停止連線到 mgc 資料庫和 mgccomp 資料庫的所有持久聊天伺服器。
    
    > [!IMPORTANT]
    > 次要持續聊天伺服器上的 SQL Server 代理程式應該在特許帳戶下執行。 具體說來, 帳戶必須包括: 
  
   - 讀取備份所要加入的網路共用的存取權。
    
   - 寫入要複本備份之特定本機目錄的存取權。
    
2. 停用備份 mgc 資料庫上的鏡像:
    
   - 使用 SQL Server Management Studio, 連線至備份 mgc 實例。
    
   - 以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 然後按一下 [**鏡像**]。
    
   - 按一下 [**移除鏡像**]。
    
   - 按一下 [確定]****。
    
   - 對 mgccomp 資料庫執行相同的步驟。
    
3. 備份 mgc 資料庫, 以便將它還原到新的主資料庫:
    
   - 使用 SQL Server Management Studio, 連線至備份 mgc 實例。
    
   - 以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 然後按一下 [**備份**]。 [**備份資料庫**] 對話方塊隨即出現。
    
   - 在 [**備份類型**] 中, 選取 [**全**選]。
    
   - 針對 [**備份元件**], 按一下 [**資料庫**]。
    
   - 要麼接受**名稱**中建議的預設備份組名稱, 要麼為備份組輸入不同的名稱。
    
   -  * \<選用\> * 在 [**描述**] 中, 輸入備份組的描述。
    
   - 從目的地清單移除預設備份位置。
    
   - 使用您為記錄傳送建立的共用位置路徑, 將檔案新增至清單。 這個路徑可供主要資料庫和備份資料庫使用。
    
   - 按一下 **[確定**] 以關閉對話方塊並開始備份程式。
    
4. 使用在上一個步驟中建立的備份資料庫來還原主要資料庫。
    
   - 使用 SQL Server Management Studio, 連線到主要的 mgc 實例。
    
   - 以滑鼠右鍵按一下 mgc 資料庫, 指向 [**任務**], 指向 [**還原**], 然後按一下 [**資料庫**]。 [**還原資料庫**] 對話方塊隨即出現。
    
   - 選取 [**從裝置**]。
    
   - 按一下 [流覽] 按鈕, 即可開啟 [**指定備份**] 對話方塊。 在 [**備份媒體**] **** 中, 選取 [檔案]。 按一下 [**新增**], 選取您在步驟3中建立的備份檔案, 然後按一下 **[確定]**。
    
   - 在 [**選取要還原的備份組**] 中, 選取 [備份]。
    
   - 按一下 [**選取頁面**] 窗格中的 [**選項**]。
    
   - 在 [**還原選項**] 中, 選取 **[覆寫現有的資料庫**]。
    
   - 在 [**恢復狀態**] 中, 選取 **[讓資料庫可供使用**]。
    
   - 按一下 **[確定]** 以開始還原程式。
    
5. 為主要資料庫設定 SQL Server 記錄傳送。 請遵循在[商務用 Skype server 2015 中設定持續聊天伺服器的高可用性和災難](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)復原中的程式, 以建立主要 mgc 資料庫的記錄傳送。
    
6. 設定持續聊天伺服器的使用中伺服器。 從商務用 Skype Server Management Shell, 使用**CsPersistentChatActiveServer** Cmdlet 來設定作用中伺服器的清單。
    
    > [!IMPORTANT]
    > 所有的作用中伺服器都必須位於與新的主資料庫相同的資料中心內, 或是在具有低延遲/高頻寬連接的資料中心中。 
  
若要將池還原到其正常狀態, 請執行下列 Windows PowerShell 命令:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

如需詳細資訊, 請參閱[CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) Cmdlet 的說明主題。
  

