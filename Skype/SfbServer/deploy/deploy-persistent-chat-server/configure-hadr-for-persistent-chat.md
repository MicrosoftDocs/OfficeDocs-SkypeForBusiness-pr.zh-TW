---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復。
ms.openlocfilehash: d7f7863a6f1a7ccc6310b8b60f7fc7cc233c29d500d01c06d6143489705306f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314899"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復。
  
商務用 Skype Server 支援後端伺服器（包括資料庫鏡像）的多種高可用性模式。 如需詳細資訊，請參閱[商務用 Skype Server 2015 的高可用性和嚴重損壞修復方案](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Persistent Chat Server 不支援 AlwaysOn 可用性群組。 

> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。
  
設定持續性聊天部署以取得高可用性和嚴重損壞修復之前，請務必熟悉在[商務用 Skype Server 2015 中規劃 persistent chat Server 的高可用性和嚴重損壞修復](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)的概念。 下列主題中所述之 Persistent Chat Server 的嚴重損壞復原解決方案是在延伸的持久聊天伺服器集區上建立。 規劃內容描述資源需求，以及可為 Persistent Chat Server 啟用高可用性和嚴重損壞修復的延伸集區拓撲，包括使用 SQL Server 鏡像以取得高可用性和 SQL Server 記錄傳送，以進行嚴重損壞修復。
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>使用拓撲產生器來設定高可用性和嚴重損壞修復

在 [拓撲產生器] 中，執行下列步驟，以設定 Persistent Chat Server 的高可用性和嚴重損壞修復。
  
1. 新增鏡像資料庫和記錄傳送次要資料庫 SQL Server 儲存區。
    
2. 編輯 Persistent Chat Server 服務屬性，使其：
    
    a. 啟用主資料庫的鏡像。
    
    b. 新增主要鏡像 SQL Server 儲存區。
    
    c. 啟用 SQL Server 記錄傳送資料庫。
    
    d. 新增 SQL Server 記錄傳送次要 SQL Server 存放區。
    
    e. 為次要資料庫新增 SQL Server 儲存區鏡像。
    
    f. 發行拓撲。
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>設定 Persistent Chat Server 主資料庫的 SQL Server 記錄傳送

使用 SQL Server Management Studio 連線到 Persistent Chat Server 次要記錄傳送資料庫實例，並確定 SQL Server 代理程式正在執行。 然後，連接至 Persistent Chat 主要資料庫實例，並執行下列步驟：
  
1. 用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。
    
2. 在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。
    
3. 選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。
    
4. 在 [交易記錄備份] 底下，按一下 [備份設定]。
    
5. 在 [備份資料夾的網路路徑] 方塊中，輸入您為交易記錄備份資料夾建立之共用的網路路徑。
    
6. 如果備份資料夾位在主要伺服器上，請在 [如果備份資料夾位於主要伺服器上，請輸入至該資料夾的本機路徑 (範例: c:\backup):] 方塊中輸入備份資料夾的本機路徑。(如果備份資料夾不在主要伺服器上，可將此方塊保留空白。)
    
    > [!IMPORTANT]
    > 若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。 
  
7. 設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。
    
8. 查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。 若要自訂安裝的排程，請按一下 [**排程**]，然後視需要調整 SQL Server 代理人排程。
    
9. 在 [壓縮] 底下選取 [使用預設伺服器設定]，然後按一下 [確定]。
    
10. 在 [次要伺服器執行個體與資料庫] 底下，按一下 [新增]。
    
11. 按一下 [**連線**]，並聯機至您已設定為次要伺服器的 SQL Server 實例。
    
12. 在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。
    
13. 在 [ **初始化次要資料庫** ] 索引標籤上，選擇 [ **是]，產生主資料庫的完整備份，並將其還原至次要資料庫 (，並在) 中建立次要資料庫**。
    
14. 在 [複製檔案] 索引標籤上的 [複製之檔案的目的資料夾] 方塊中，輸入複製交易記錄備份的目的資料夾路徑。此資料夾通常位在次要伺服器上。
    
15. 在 [複製工作] 底下，注意列示在 [排程] 方塊中的複製排程。 若要自訂安裝的排程，請按一下 [**排程**]，然後視需要調整 SQL Server 代理人排程。 此排程應與備份排程大致相同。
    
16. 在 [還原] 索引標籤上的 [還原備份時的資料庫狀態] 底下，選擇 [不復原模式] 選項。
    
17. 在 [延遲還原備份至少:] 底下，選取 [0 分鐘]。
    
18. 在 [如果未在此時間內進行還原，則發出警示] 底下，選擇警示臨界值。
    
19. 在 [還原工作] 底下，查看列示在 [排程] 方塊中的還原排程。 若要自訂安裝的排程，請按一下 [**排程**]，然後視需要調整 SQL Server 代理程式排程，然後按一下 **[確定]**。 此排程應與備份排程大致相同。
    
20. 在 [資料庫內容] 對話方塊上按一下 [確定]，即開始設定程序。
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>設定主要鏡像與次要資料庫之間的 SQL Server 記錄傳送

若主要持久聊天資料庫容錯移轉至其鏡像資料庫，請執行下列步驟，以繼續進行記錄傳送。
  
1. 手動將主要持久聊天資料庫容錯移轉至鏡像。 這是透過使用商務用 Skype Server 管理命令介面和 **Invoke-CsDatabaseFailover** Cmdlet 來完成。
    
2. 使用 SQL Server Management Studio 連接至主要 Persistent Chat Server 鏡像實例。
    
3. 請確定 SQL Server 代理程式正在執行中。
    
4. 用滑鼠右鍵按一下 mgc 資料庫，然後按一下 **[屬性]**。
    
5. 在 **[選取頁面]** 下，按一下 **[交易記錄傳送]**。
    
6. 選取 **[將此啟用為記錄傳送組態的主要資料庫]** 核取方塊。
    
7. 在 **[交易記錄備份]** 下，按一下 **[備份設定]**。
    
8. 在 **[備份資料夾的網路路徑]** 方塊中，鍵入您為異動記錄備份資料夾所建立的共用的網路路徑。
    
9. 如果備份資料夾位於主要伺服器上，請在 **[如果備份資料夾位於主要伺服器上，請輸入至該資料夾的本機路徑]** 方塊中鍵入備份資料夾的本機路徑 (如果備份資料夾不是在主要伺服器上，您可以不要選取此方塊)。
    
    > [!IMPORTANT]
    > 若主伺服器上的 SQL Server 服務帳戶是在本機系統帳戶之下執行，則必須在主伺服器上建立備份檔案夾，並指定該資料夾的本機路徑。 
  
10. 設定 **[指定刪除檔案的時限]** 和 **[如果未在此時間內進行備份，則發出警示]** 參數。
    
11. 查看列在 **[備份作業]** 下的 **[排程]** 方塊中的備份排程。 若要自訂安裝的排程，請按一下 [**排程**]，然後視需要調整 SQL Server 代理人排程。
    
    > [!IMPORTANT]
    > 使用和主要資料庫相同的設定。 
  
12. 在 **[壓縮]** 下，選取 **[使用預設伺服器設定]**，然後按一下 **[確定]**。
    
13. 在 **[次要伺服器執行個體與資料庫]** 下，按一下 **[新增]**。
    
14. 按一下 **[連線]**，然後連線至您已設定為次要伺服器的 SQL Server 的執行個體。
    
15. 在 **[次要資料庫]** 方塊中，從清單中選取 **[mgc]** 資料庫。
    
16. 在 **[初始化次要資料庫]** 索引標籤上，選取選項 **[否，次要資料庫已初始化]**。
    
17. 在 **[複製檔案]** 索引標籤的 **[複製之檔案的目的資料夾]** 中，鍵入應複製異動記錄備份的資料夾的路徑，然後按一下 **[確定]**。這個資料夾通常位於次要伺服器上。
    
18. 開啟 **[指令碼設定]** 下拉式清單，然後選取 **[編寫組態的指令碼至新增查詢視窗]**。
    
19. 在新增查詢視窗的 **[資料庫屬性]** 中，按一下 **[確定]** 開始設定程序。
    
20. 選取並執行查詢的前半部 (請參閱 step 18) 至行：-- \* \* \* \* \* \* End： Script to 執行主要： \* \* \* \* \* \* 。
    
    > [!IMPORTANT]
    > 手動執行此腳本是必要的，因為 SQL Server Management Studio 不支援 SQL Server 記錄傳送設定中的多個主資料庫。 
  
21. 選取 **[取消]** 以關閉記錄檔傳送設定面板，然後建立工作設定，正確實作主要和鏡像資料庫 (若容錯移轉) 的記錄檔傳送。
    
22. 手動將主要持久聊天資料庫回復回主要。 這是透過使用商務用 Skype Server 管理命令介面和 **Invoke-CsDatabaseFailover** Cmdlet 來完成。
    

