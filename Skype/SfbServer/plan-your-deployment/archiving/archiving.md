---
title: 在商務用 Skype Server 中進行歸檔規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 中規劃封存。'
ms.openlocfilehash: 9d24457d8345aa6b496489b68347a98c069abc69
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193987"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>在商務用 Skype Server 中進行歸檔規劃
 
**摘要:** 請閱讀本主題, 以瞭解如何在商務用 Skype Server 中規劃封存。
  
公司和其他組織必須遵守特定類型的通訊所需的行業及政府管理條例數量。 如果您的組織有這些需求, 您可以在商務用 Skype Server 中使用封存來封存立即訊息 (IM) 與會議 (會議) 通訊, 以協助支援您的一些規範需求。
  
## <a name="archiving-components"></a>封存元件

商務用 Skype 伺服器使用下列存檔元件:
  
- 封存**代理**程式。 封存代理程式 (又稱為「整合資料收集代理程式」) 是在每個企業版前端池和標準版伺服器上自動安裝並啟用。 雖然封存代理程式會自動啟用, 但在啟用封存並適當設定前, 不會實際捕獲任何訊息。 根據預設, 封存是停用的。
    
- **歸檔資料儲存空間**。 商務用 skype Server 的資料儲存空間可以做為商務用 Skype Server SQL Server 資料庫, 或者, 如果您有 Exchange 部署 (與 Exchange 存儲整合), 請執行此選項。 
    
封存也需要檔案儲存空間, 但封存會使用與前端伺服器或標準版伺服器相同的檔案儲存空間。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>判斷貴組織的存檔需求

若要實施封存, 您必須決定下列專案, 以決定如何滿足貴組織的存檔需求:
  
- **要使用的儲存空間選項**。 您可以使用兩種方法的其中一種來實現儲存空間, 或同時使用兩者的組合:
    
  - **Exchange 儲存空間。** 如果您有 Exchange 部署, 您可以整合商務用 Skype Server 與 Exchange 封存, 讓您的商務用 Skype 伺服器與 Exchange 封存的資料都儲存在 Exchange 中。 如果您啟用 Microsoft Exchange 整合選項, 則駐留在 Exchange 伺服器上的使用者信箱會將 Exchange 儲存空間用於已歸檔的資料, 但只有在已將信箱放在就地保留中的情況下。 根據預設, 不會啟用 Microsoft Exchange 整合。
    
  - **商務用 Skype Server 儲存空間。** 如果您的使用者不是駐留在 Exchange 上, 或未將其信箱放在就地保留中, 或是您不想要在部署中的任何或所有使用者都使用 Microsoft Exchange 整合, 您可以使用 S 部署商務用 Skype Server 封存資料庫QL [伺服器]。
    
- **部署存檔**的時機。 您可以將封存部署為您最初的商務用 Skype Server 部署的一部分, 或者您可以將它新增到現有的部署。 若要使用商務用 Skype Server 封存儲存空間 (SQL Server 資料庫), 您可以使用 [拓撲建立器] 將資料庫新增到拓撲結構, 然後再次發佈拓撲。 如果您的所有使用者都是以 Exchange 為宿主, 且其信箱放在就地保留中, 則您不需要更新您的拓撲, 只需要啟用 Microsoft Exchange 整合, 即可在 Exchange 中儲存已歸檔的資料。 
    
- **組織中的哪些網站和使用者需要**封存。 您可以為整個組織設定封存設定, 也可以針對特定網站、池、使用者和使用者群組設定存檔設定。
    
- **應該封存哪些內容**。 無論您是在全域層級或是針對特定網站和使用者指定封存, 您可以指定是否要啟用下列類型的內容: 
    
  - 對等立即訊息
    
  - 會議 (會議), 這是多方立即訊息
    
  - 會議內容, 包括上傳的內容 (例如講義) 及事件相關內容 (例如加入、離開、上傳共用, 以及在可見度中變更)
    
  - 在會議期間共用白板和投票
    
- **無法歸檔哪些內容**。 下列內容類型無法歸檔: 
    
  - 對等檔案傳輸
    
  - 對等立即訊息與會議的音訊/視頻
    
  - 對等立即訊息和會議的桌面與應用程式共用
    
    商務用 Skype 伺服器也不會封存持久聊天交談。 若要封存持久的聊天交談, 您必須啟用並設定合規性服務, 這是可使用持久聊天伺服器部署的元件。 如需詳細資訊, 請參閱[在商務用 Skype server 2015 中規劃持久聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

    > [!NOTE] 
    > 商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。 
    
- 已**歸檔的資料應保留**多久。 存檔資料庫不是用於長期保留, 商務用 Skype 伺服器不會提供電子探索 (搜尋) 方案來儲存已歸檔的資料, 因此需要將資料移到其他儲存空間。 商務用 Skype 伺服器提供您可以用來匯出封存資料的會話匯出工具, 這會建立已歸檔資料的可搜尋記錄。 
    
     針對全域原則, 以及您建立的每個網站和使用者原則, 您可以指定何時清除封存和匯出的資料。 如需有關清除資料的詳細資訊, 請參閱[管理商務用 Skype Server 中的已歸檔資料清除](../../manage/archiving/purging-of-archived-data.md)。 如需有關使用會話匯出工具的詳細資訊, 請參閱[在商務用 Skype Server 中匯出封存的資料](../../manage/archiving/export-archived-data.md)。
    
- **是否封存內部或外部通訊**。 您可以針對內部通訊 (內部使用者之間的通訊)、外部通訊 (至少包含一個使用者在內部網路以外的通訊), 或兩者皆啟用封存。 您可以為整個組織指定這些選項, 也可以針對特定的網站和池加以指定。 預設不會啟用任何選項。
    
    > [!NOTE]
    > 只有商務用 Skype 原則才能使用控制內部或外部通訊的封存。 針對 Exchange 整合式封存, 內部和外部通訊都已歸檔或未歸檔。 
  
- **是否要實現重要模式**。 如果您的組織需要進行封存, 設定 [重要] 模式時, 會封鎖 IM 和會議會話, 以免發生可避免封存之商務用 Skype 伺服器失敗的情況。 例如： 
    
  - 商務用 Skype Server storage service 的問題。 在這種情況下, 會封鎖已啟用封存功能的使用者的 IM。
    
  - 無法使用的檔案共用或儲存服務的問題。 在此情況下，所有於失敗時間在集區中進行的會議，都會切換為限制模式，而且無法啟動新的會議。
    
    IM 和會議會在更正失敗之後自動復原。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>選擇 [封存部署與設定選項]

當您部署伺服器時, 會在每個前端伺服器上自動安裝封存, 但除非您設定存檔, 否則不會啟用封存。 設定存檔的方式取決於您的部署方式。 您可以採用下列其中一種方式部署封存:
  
- 使用 Microsoft Exchange 儲存空間
    
- 使用商務用 Skype Server storage
    
> [!NOTE]
> 如果您同時執行的是商務用 Skype Server 封存資料庫並啟用 Microsoft Exchange 整合, Exchange 原則會覆寫商務用 Skype Server 封存原則, 但只適用于駐留在 Exchange 且其信箱放在 Exchange 中的使用者就地保留。 商務用 Skype 存檔取決於 Microsoft Exchange 就地保留原則。 
  
如果您要部署一個前端池或標準版伺服器的封存, 您應該針對部署中的所有其他前端池和標準版伺服器啟用該歸檔。 如果在託管或會議所在的池中未啟用 [封存], 所有的會議資料都可能無法封存。 存檔仍適用于 IM 郵件, 但會議內容和事件可能不會封存。
  
> [!NOTE]
> 若要在維護貴組織的安全性標準時啟用管理工作委派, 商務用 Skype 伺服器會使用角色式存取控制 (RBAC)。 使用 RBAC, 系統會將使用者指派至預先定義的管理角色, 以獲得系統管理許可權。 若要設定商務用 Skype 封存原則和設定, 必須將使用者指派給 CsArchivingAdministrator 角色 (除非是直接在部署歸檔的伺服器上執行, 而不是從另一部電腦遠端完成)。). 如需封存部署所需的使用者權利、許可權和角色清單, 請參閱[部署商務用 Skype Server](../../deploy/deploy-archiving/deploy-archiving.md)的封存。 
  
> [!NOTE]
> 如果您使用的是 Microsoft Exchange 整合, 則 Exchange 原則的設定需要適當的系統管理員權力和許可權。 如需詳細資訊, 請參閱 Exchange 檔。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 儲存空間

 如果您選擇 [Microsoft Exchange 整合], 您可以使用 Exchange 原則和設定來控制商務用 Skype Server 的存檔。 您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定 Microsoft Exchange 整合選項。 如果您的部署包含多個目錄林, 您必須同步處理商務用 Skype Server 與 Exchange 之間的設定。 您將需要判斷:
  
- 是否要封存 IM、會議或兩者
    
- 是否要實現重要模式, 以在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話 
    
- 選取 [Microsoft Exchange 整合] 選項以使用 Exchange 儲存已歸檔資料
    
如需如何設定 Exchange 就地保留原則和設定以支援封存的相關資訊, 請參閱 Exchange 產品檔。
  
### <a name="skype-for-business-server-storage"></a>商務用 Skype Server storage

如果您選擇 [商務用 Skype Server storage], 您可以使用商務用 Skype 伺服器的歸檔原則和設定來控制如何啟用及實施封存。 商務用 Skype Server storage 使用 SQL Server 資料庫, 因此您必須將適當的 SQL Server 資料庫新增到您的拓撲結構中, 然後再設定您的存檔原則。 
  
### <a name="add-storage-databases-to-your-topology"></a>在拓撲中新增儲存空間資料庫

在您的拓撲中新增 SQL Server storage 資料庫時, 您可以選擇使用下列任何一項 collocate 存檔資料庫:
  
- 監控資料庫
    
- 企業版頂層端池的後端資料庫
    
> [!NOTE]
> 裝載存檔資料庫的伺服器可以裝載其他資料庫。 不過, 當您考慮將封存資料庫與其他資料庫 collocating 時, 請注意, 如果您要封存的郵件超過幾個使用者, 存檔資料庫所需的磁碟空間就會變得很大。 基於這個原因, 我們不建議您 collocating 封存資料庫與後端資料庫。 
  
如果您使用監視資料庫、後端資料庫或這兩個資料庫 collocate 封存資料庫, 您可以針對任何或所有資料庫使用單一 SQL 實例, 或者, 您也可以針對每個資料庫使用個別的 SQL 實例, 包括下列各項:限制: 每個 SQL 實例只能包含一個後端資料庫、單一監視資料庫及單一存檔資料庫。
  
如需 collocation 所有伺服器角色和資料庫的詳細資料, 請參閱[商務用 Skype server 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。 如需更新拓撲以包含儲存資料庫的詳細資料, 請參閱[在商務用 Skype Server 中建立及發佈新的拓撲](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>決定存檔選項和使用者原則

您將需要判斷:
  
- 是否要啟用或停用內部與外部通訊的封存
    
- 是否要封存 IM、會議或兩者
    
- 是否要實現重要模式, 以在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話 
    
- 是否要針對特定的使用者和群組啟用原則
    
商務用 Skype Server 封存選項可以在下列層面上指定。 
  
- **全域層次選項**。 這是預設的存檔設定, 且適用于整個部署。 它是在您部署商務用 Skype Server 時建立的, 而且根據預設, 會停用內部與外部通訊的存檔。 您無法刪除此選項。 如果您選擇 [刪除] 選項, [全域] 選項會重設為預設設定。
    
- **網站層級選項**。 您可以建立及設定網站的網站層級歸檔選項, 以啟用或停用一或多個特定網站的封存。 您可以刪除任何您建立的網站層級存檔選項。 網站層級的存檔選項會覆寫全域選項, 但只適用于選項中指定的網站。 
    
    例如, 如果您在全域設定中啟用內部和外部通訊的封存, 並建立您在其中停用外部通訊封存的網站設定, 則只有內部通訊會針對該網站進行歸檔。 在其他範例中, 如果您只針對全域設定中的 IM 啟用 [封存], 並建立可讓 IM 與會議進行封存的網站設定, 會議只會針對網站進行歸檔, 而不會針對您的其餘部分進行封存機構.
    
- [**池] 層級選項**。 您可以為個別的池建立和設定池層級設定, 以指定一或多個特定池的存檔設定。 池層級的歸檔設定只有在您建立時才存在。 您可以修改並刪除任何池層級的存檔設定。 池層級的存檔設定會覆寫全域設定和您可能已建立的任何網站封存設定。 
    
    例如, 假設您只在全域設定中啟用 IM 的封存, 然後建立網站層級設定, 讓您在 IM 和會議中啟用封存, 然後建立一層級設定, 讓您只針對 IM 啟用存檔功能. 除了駐留在 pool 階層設定中指定的池中的使用者以外, 對於網站的所有使用者, 都會將 IM 和會議的通訊進行歸檔。 針對貴組織中的所有其他使用者, 只會針對 IM 啟用封存功能。
    
- **使用者歸檔原則**。 您可以針對特定的使用者和使用者群組建立、設定及套用使用者層級歸檔原則, 以啟用或停用一或多個特定使用者與使用者群組的封存。 您可以刪除您建立的任何使用者層級歸檔原則, 而且您可以變更封存原則適用的使用者和使用者組。 使用者層級的歸檔原則會覆寫全域原則和任何網站原則, 但只適用于已套用原則的使用者和使用者群組。 
    
    例如, 假設您在全域設定中停用內部和外部通訊的封存, 建立網站層級原則, 您可以在其中啟用內部和外部通訊的封存, 然後建立使用者層級原則, 您可以在其中停用封存外部通訊。 除了您套用使用者層級原則的使用者之外, 所有網站使用者的外部與內部通訊都要封存通訊, 但這些使用者只會封存內部通訊。
    
如需如何在部署存檔時設定初始封存配置的詳細資料, 請參閱[部署商務用 Skype Server](../../deploy/deploy-archiving/deploy-archiving.md)的封存。 如需在部署之後管理存檔的詳細資料, 請參閱[在商務用 Skype 伺服器中管理存檔](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>封存組態工具

 您可以使用商務用 Skype Server [控制台] 控制大部分的存檔選項。 不過, 只有使用商務用 Skype Server 管理命令介面時, 才有幾個選項可供使用。 這些選項包括存檔重複的郵件, 以及匯出封存的資料。 如需使用商務用 Skype Server 的 [控制台] 和 [商務用 Skype 伺服器管理命令介面] 管理封存原則的詳細資訊, 請參閱[管理商務用 Skype server 中](../../manage/archiving/archiving.md)的封存。
  
## <a name="access-archived-data"></a>存取已歸檔的資料

歸檔資料的存取權視資料的儲存位置而定: 
  
- **Microsoft Exchange 儲存空間**。 如果您選擇 [Exchange 整合] 選項, 商務用 Skype 伺服器會在 Exchange 市集中為所有駐留在 Exchange 的使用者, 以及將其信箱放在就地保留中的使用者, 為其儲存存檔內容。 已歸檔的資料會儲存在 [使用者信箱可復原的專案] 資料夾中, 使用者通常會看不到該資料夾, 而且只有擁有 Exchange**探索管理**角色的使用者才能進行搜尋。 Exchange 可在已部署的情況下, 與 SharePoint 一起啟用同盟搜尋與探索。 如需有關儲存在 Exchange 中之資料的儲存、保留和探索的詳細資訊, 請參閱 Exchange 與 SharePoint 檔。
    
- **商務用 Skype 伺服器封存儲存空間**。 如果您已設定商務用 Skype Server 封存資料庫, 商務用 Skype 伺服器會將存檔內容儲存在商務用 Skype 伺服器封存資料庫中, 以供未駐留在 Exchange 的任何使用者使用, 且未將其信箱放在適當位置。 此資料是無法搜尋的, 但可將其匯出為可使用其他工具搜尋的格式。 如需有關匯出儲存在歸檔資料庫中之資料的詳細資訊, 請參閱[在商務用 Skype Server 中匯出封存的資料](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>如需詳細資訊

如需有關存檔的詳細資訊, 請參閱下列主題:
  
- [部署商務用 Skype Server 的存檔](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [在商務用 Skype Server 中管理存檔](../../manage/archiving/archiving.md)
    
如需有關商務用 Skype Server 與 Exchange 共同作業方式的詳細資訊, 請參閱[規劃整合商務用 skype 與 exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  

