---
title: 將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6b4f4d69-3c9d-4bc7-bc9b-46427a095de2
description: 摘要：閱讀此主題以瞭解如何將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲。
---

# <a name="add-persistent-chat-server-to-your-skype-for-business-server-2015-topology"></a>將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲
 
**總結：** 閱讀此主題以瞭解如何將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲。
  
在您計畫部署 Persistent Chat Server 的每部伺服器上安裝必要軟體之後，您可以使用拓撲產生器來執行下列作業： 
  
- 更新您的拓撲以包含 Persistent Chat Server
    
- 發行更新的拓撲
    
> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

## <a name="update-your-topology-to-include-persistent-chat-server"></a>更新您的拓撲以包含 Persistent Chat Server

請執行下列步驟來安裝單一持久聊天伺服器集區，而不需要災難修復設定。 若要設定高可用性和嚴重損壞修復的延伸持久聊天伺服器集區，請參閱[在商務用 Skype Server 2015 中設定 Persistent chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。
  
若要部署多個 Persistent Chat Server 集區，請對每個集區重複相同的程式。
  
1. 在執行商務用 Skype Server 的電腦上，或已安裝商務用 Skype Server 系統管理工具的電腦上，使用本機 Users 群組成員的帳戶登入， (或) 具有同等使用者權限的帳戶。
    
    > [!NOTE]
    > 您可以使用本機 Users 群組成員的帳戶來定義拓撲，不過，若要發行的拓撲是安裝商務用 Skype Server 所需的，您必須使用屬於 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 群組成員的帳戶，且具有您要用於 Persistent Chat Server 檔案之檔案存放區的「完全控制」許可權 (讀取、寫入及修改) 。 儲存 (，讓拓撲產生器可以設定所需的 Dacl) 或具有同等權利的帳戶。
  
2. 啟動拓撲產生器。
    
3. 在主控台樹中，流覽至 [ **Persistent Chat** 集區] 節點，並展開以選取商務用 Skype Server 集區，或在節點上按一下滑鼠右鍵，然後選取 [**新增持久聊天集** 區]。 您必須定義集區的完整功能變數名稱 (FQDN) ，並指出集區將會是單一伺服器集區還是多伺服器集區部署。
    
    您可以選擇 [多重電腦集區] 或 [單一電腦集區]。 如果您打算在持久聊天伺服器集區中有多部前端伺服器，請選擇前者。 立即或稍後選擇，這是因為建立單一電腦集區後，稍後便無法新增其他伺服器。 如果您選擇 [多部電腦集區]，請輸入組成集區之個別前端伺服器的名稱。
    
    > [!IMPORTANT]
    > 若要在 Standard Edition 伺服器上安裝 Persistent Chat Server role，fqdn 必須符合 Standard Edition 伺服器的 fqdn。 
  
4. 定義 Persistent Chat Server 集區的簡易 **顯示名稱** 。 顯示名稱可供自訂用戶端使用，特別是在有多個 Persistent Chat Server 集區來區分會議室時。
    
5. 定義 Persistent Chat Server 使用的埠，以與商務用 Skype Server 前端伺服器進行通訊。 預設的連接埠為 5041。
    
6. 如果您的組織需要規範支援，請選取 [用規範記錄] 核取方塊。 如有選取，Persistent Chat Server 規範服務會與 Persistent Chat Server 前端伺服器安裝在相同的電腦上。 稍後會提示您為 Persistent Chat server 相容性選取 SQL Server 後端伺服器。
    
7. 為 Persistent Chat Server 集區指派網站相關性。 選取 [**使用此集區作為網站 \<SiteName\> 預設值**] 核取方塊，或 **使用此集區作為所有網站的預設** 值，將此 Persistent Chat Server 集區指定為目前網站或所有網站的預設集區。 當使用商務用 Skype 用戶端來建立及管理聊天室時，會使用與使用者網站相關聯的預設集區建立和管理經驗，使其可以將會議室建立和管理作業路由傳送至該集區。 這只有當您部署多個 Persistent Chat Server 集區，且想要使用 Persistent Chat Server 的聊天室建立及管理功能時，才適用。
    
    > [!IMPORTANT]
    > 您可以使用 Persistent Chat Server 軟體發展工具組 (SDK) ，自訂聊天室建立和管理功能。 
  
8. 透過執行下列其中一項操作，**為 Persistent chat Server 後端 (定義 SQL 儲存區)** ：
    
   - 若要使用現有的 SQL Server 儲存區，請在下拉式清單中，按一下您要使用的 SQL Server 儲存區名稱。
    
   - 若要指定新的 SQL Server 資料庫，請按一下 [**新增**]，然後在 [**定義新的 SQL 存放區**] 中，執行下列作業：
    
   - 在 [ **SQL Server fqdn**] 中，指定您要建立新 SQL Server 資料庫之 SQL Server 的 FQDN。
    
   - 選取 [預設執行個體] 使用預設執行個體，或者，若要指定不同的執行個體，請選取 [具名執行個體]，並指定要使用的執行個體。
    
     > [!NOTE]
     > 如需如何設定 SQL Server 備份資料庫以進行嚴重損壞修復的詳細資訊，請參閱[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
9. 如果您已啟用規範，請定義 SQL Server 規範儲存區。
    
    > [!IMPORTANT]
    > 如需如何針對 persistent chat server 資料庫和 persistent chat server 規範資料庫設定高可用性的 SQL Server 鏡像，請參閱[在商務用 Skype Server 2015 中設定 persistent chat server 的高可用性和嚴重損壞修復](../../deploy/deploy-high-availability-and-disaster-recovery/configure-hadr-for-persistent-chat.md)。 
  
10. 定義檔案存放區。 檔案存放區是儲存任何上傳至檔案儲存機制的檔案副本所用的資料夾 (例如，儲存張貼於聊天室的檔案附件)。 在多重伺服器持久聊天伺服器拓撲的情況下，這必須是通用命名慣例 (UNC) 路徑;而且，針對單一伺服器的持久聊天伺服器拓撲，它可以是本機檔路徑。
    
    若要使用現有的檔案存放區，請執行下列動作：
    
    - 在 [ **檔案伺服器 FQDN**] 中，指定您要建立新檔案存放區之機器的 FQDN。
    
    - 在 [檔案共用] 中，指定要使用的檔案存放區。
    
      > [!IMPORTANT]
      > 您可以在建立檔案存放區之前，先在拓撲產生器中定義檔案存放區，但是您必須先在您定義的位置中建立檔案存放區，然後才能發行拓撲。 如果檔案存放區尚不存在，則嘗試發行拓撲會失敗。 
  
11. 選取此 Persistent Chat Server 集區的下一個躍點要使用的前端伺服器集區。 這是可以將 Persistent Chat Server 要求路由傳送至此集區的前端伺服器集區。
    
12. 若要儲存組態，請按一下 [完成]。 Persistent Chat Server 集區會出現在拓撲產生器中，且附帶您的特定集區設定。
    
    若要發行您已新增持久聊天伺服器的更新拓撲，請參閱發行更新的拓撲。
    
    > [!NOTE]
    > 在已開啟拓撲產生器的情況下，您可以繼續進行步驟3發行更新的拓撲，以開始發行更新的拓撲。 
  
## <a name="publish-the-updated-topology"></a>發行更新的拓撲
<a name="BKMK_PublishTopology"> </a>

在拓撲產生器中更新拓撲之後，您必須將拓撲發佈至中央管理存放區，才能設定及使用商務用 Skype Server。 資料的唯讀複本會複製到拓撲中的所有伺服器，讓所有伺服器與拓撲和其他設定變更保持同步。
  
在發佈拓撲之前，請安裝 Persistent Chat Server 的資料庫。 使用拓撲產生器，選取 [ **動作** ] 並 **安裝資料庫** 以安裝資料庫。
  
1. 在執行商務用 Skype Server 的電腦上，或已安裝商務用 Skype Server 系統管理工具的電腦上，使用 **Domain Admins** 群組和 **RTCUniversalServerAdmins** 成員的帳戶登入。 群組，且具有對要用於 Persistent Chat Server 檔存放 (區之檔案存放區的「完全控制」許可權 (讀取、寫入及修改) ，使拓撲產生器可以設定所需的任意自由存取控制清單 (Dacl) ) ，或具有同等使用者權限的帳戶。
    
2. 啟動拓撲產生器。 如果您已在本機儲存，請從本機檔案選取 [ **開啟拓撲** ]。
    
3. 在主控台樹中，以滑鼠右鍵按一下 [**商務用 Skype Server 2015**]，然後按一下 [**發行拓撲**]。
    
4. 在 **[發行拓撲]** 頁面上，按 **[下一步]**。
    
5. 在 **[發行精靈完成]** 頁面上，確認拓撲已成功發行，然後按一下 **[完成]**。
    

