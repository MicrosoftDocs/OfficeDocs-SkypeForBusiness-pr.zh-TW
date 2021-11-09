---
title: 在商務用 Skype Server 中規劃封存
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中規劃封存。
ms.openlocfilehash: 6d67caa4b196c65282ecb404af747e0a60f435a7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843696"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃封存
 
**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中規劃封存。
  
公司和其他組織會遭受不斷增加的行業和政府法規數量，需要保留特定類型的通訊。 如果您的組織有這樣的需求，您可以使用商務用 Skype Server 中的封存，封存立即訊息 (IM) 和會議 (會議) 通訊，以協助支援一些規範需求。
  
## <a name="archiving-components"></a>封存元件

商務用 Skype Server 會使用下列封存元件：
  
- **封存代理程式**。 封存代理程式 (也稱為「整合資料收集代理程式」) 會在每個 Enterprise Edition 前端集區和 Standard Edition 伺服器上自動安裝及啟用。 雖然封存代理程式會自動啟動，但在啟用封存並適當設定封存之前，不會實際捕獲任何郵件。 預設會停用封存。
    
- **封存資料存放區**。 商務用 Skype Server 的資料儲存區的實施方式可以是商務用 Skype Server SQL Server 資料庫，或者，如果您有 Exchange 的部署，且已與 Exchange 儲存區整合。 
    
封存也需要檔案存放區，但是封存會使用與前端伺服器或 Standard Edition 伺服器相同的檔案存放區。

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>決定組織的封存需求

若要執行封存，您必須決定下列專案，以決定如何符合組織的封存需求：
  
- **要使用的儲存體選項**。 您可以使用下列其中一種方式或同時使用二者的組合來執行存放區：
    
  - **Exchange 儲存區。** 如果您有 Exchange 部署，您可以整合商務用 Skype Server 和 Exchange 封存，使商務用 Skype Server 及 Exchange 封存的資料會一起儲存在 Exchange 中。 如果您啟用 Microsoft Exchange 整合選項，則 Exchange Server 中的使用者信箱會使用封存資料的 Exchange 儲存區，但只有在信箱已設 In-Place 保留狀態時才使用。 依預設，不會啟用 Microsoft Exchange 整合。
    
  - **商務用 Skype Server 儲存區。** 如果您有沒有位於 Exchange 所在的使用者，或是未將其信箱置於 In-Place 保留狀態，或者您不想使用 Microsoft Exchange 整合部署中的任何或所有使用者，您可以使用 SQL Server 部署商務用 Skype Server 的封存資料庫。
    
- **何時部署** 封存。 您可以部署封存做為初始商務用 Skype Server 部署的一部分，也可以將它新增至現有的部署。 若要使用商務用 Skype Server 封存儲存 (SQL Server 資料庫) ，您可以使用拓撲產生器將資料庫新增至您的拓撲，然後再發行拓撲。 如果您的所有使用者都位於 Exchange，並將其信箱置於 In-Place 保留狀態，您就不需要更新拓撲，但只需要啟用 Microsoft Exchange 整合，即可將封存的資料儲存在 Exchange 中。 
    
- **組織中的哪些網站和使用者需要** 封存。 您可以為整個組織設定封存設定，也可以為特定網站、集區、使用者和使用者群組設定封存設定。
    
- **應該封存哪些內容**。 不論是在全域層級或是針對特定網站和使用者指定封存，您會指定是否要啟用下列類型的內容： 
    
  - 對等立即訊息
    
  - 會議，其為多方立即訊息
    
  - 會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)
    
  - 在會議期間共用白板與投票
    
- **哪些內容無法** 封存。 無法封存下列類型的內容： 
    
  - 對等檔案傳輸
    
  - 對等立即訊息和會議的音訊/視訊
    
  - 對等立即訊息和會議的桌面與應用程式共用
    
    商務用 Skype Server 也不會封存持久聊天交談。 若要封存持久聊天對話，您必須啟用和設定規范服務，該服務是可與 Persistent Chat Server 一起部署的元件。 如需詳細資訊，請參閱[Plan for Persistent Chat Server in 商務用 Skype Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。

    > [!NOTE] 
    > 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
    
- **可保留的封存材料長度**。 封存資料庫不適用於長期保留，而且商務用 Skype Server 不會提供電子探索 (的封存資料的搜尋) 方案，因此資料必須移至其他儲存區。 商務用 Skype Server 提供的會話匯出工具，可供您用來匯出封存的資料，並會建立已封存資料的可搜尋記錄。 
    
     針對全域原則，以及您建立的每個網站和使用者原則，您可以指定何時清除已封存及匯出的資料。 如需清除資料的詳細資訊，請參閱[在商務用 Skype Server 中管理已封存資料的清除](../../manage/archiving/purging-of-archived-data.md)。 如需使用「會話匯出」工具的詳細資訊，請參閱[在商務用 Skype Server 中匯出封存的資料](../../manage/archiving/export-archived-data.md)。
    
- **是否封存內部或外部通訊**。 您可以對內部使用者之間的通訊 (通訊啟用內部通訊的封存) 、外部通訊 (在內部網路以外至少包含一位使用者的通訊) ，或是兩者。 您可以為整個組織指定這些選項，也可以為特定網站和集區指定這些選項。 根據預設，這兩個選項都不會啟用。
    
    > [!NOTE]
    > 控制內部或外部通訊的封存只適用于商務用 Skype 原則。 在 Exchange 整合的封存中，內部和外部通訊都是封存或未封存。 
  
- **是否要執行關鍵模式**。 如果您的組織需要封存，設定重要模式會封鎖 IM 和會議會話，以防發生商務用 Skype Server 失敗，可能會造成封存。 例如： 
    
  - 商務用 Skype Server 儲存服務的問題。 在此情況下，會封鎖已啟用封存的使用者的 IM。
    
  - 無法使用的檔案共用或儲存服務的問題。 在此情況下，所有失敗時於集區中進行的會議，都會切換為限制模式，而且無法發起新的會議。
    
    IM 和會議會在失敗更正後自動復原。
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>選擇封存部署和設定選項

當您部署伺服器時，封存會自動安裝在每一部前端伺服器上，但是除非您設定封存，否則不會啟用封存。 如何設定封存取決於您的部署方式。 您可以採用下列其中一種方式部署封存：
  
- 使用 Microsoft Exchange 儲存區
    
- 使用商務用 Skype Server 儲存區
    
> [!NOTE]
> 如果您同時執行商務用 Skype Server 封存資料庫並啟用 Microsoft Exchange 整合，Exchange 原則會覆寫商務用 Skype Server 的封存原則，但僅限於位於 Exchange 的使用者，且其信箱置於 In-Place 保留狀態。 商務用 Skype 封存取決於 Microsoft Exchange In-Place 保留原則。 
  
如果您部署一個前端集區或 Standard Edition 伺服器的封存，則應該為部署中的所有其他前端集區和 Standard Edition 伺服器啟用封存。 如果在主控交談或會議的集區上未啟用封存，所有會議資料可能都不會封存。 封存仍可用於 IM 郵件，但是會議內容和事件可能不會封存。
  
> [!NOTE]
> 若要在維護組織的安全性標準時，啟用管理工作委派，商務用 Skype Server 會使用以角色為基礎的存取控制 (RBAC) 。 透過 RBAC，系統管理許可權是透過指派使用者至預先定義的系統管理角色授與。 若要設定商務用 Skype 封存原則及設定，必須將使用者指派給 CsArchivingAdministrator 角色 (，除非在部署封存的伺服器上直接執行設定，而不是從其他電腦) 遠端執行。 如需封存部署所需之使用者權利、許可權及角色的清單，請參閱[部署商務用 Skype Server](../../deploy/deploy-archiving/deploy-archiving.md)的封存。 
  
> [!NOTE]
> 如果您使用 Microsoft Exchange 整合，設定 Exchange 原則需要適當的系統管理員許可權。 如需詳細資訊，請參閱 Exchange 檔。 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 儲存

 如果您選擇 [Microsoft Exchange 整合]，您可以使用 Exchange 原則和設定來控制商務用 Skype Server 的封存。 您可以在全域層級、網站層級及集區層級設定 Microsoft Exchange 整合選項。 如果您的部署包含多個樹系，您必須同步處理商務用 Skype Server 和 Exchange 之間的設定。 您將需要判斷：
  
- 是否要封存 IM、會議或兩者
    
- 是否要執行關鍵模式，以在商務用 Skype Server 失敗時封鎖 IM 和會議會話 
    
- 選取 Microsoft Exchange 整合選項，以使用 Exchange 儲存封存的資料
    
如需如何設定 Exchange In-Place 保留原則及設定以支援封存的詳細資訊，請參閱 Exchange 產品檔。
  
### <a name="skype-for-business-server-storage"></a>商務用 Skype Server 儲存

如果您選擇 [商務用 Skype Server 儲存]，您可以使用商務用 Skype Server 封存原則和設定來控制如何啟用及實施封存。 商務用 Skype Server 儲存體使用 SQL Server 資料庫，所以您必須將適當的 SQL Server 資料庫新增至您的拓撲，然後再設定您的封存原則。 
  
### <a name="add-storage-databases-to-your-topology"></a>將儲存資料庫新增至您的拓撲

將 SQL Server 儲存資料庫新增至您的拓撲時，您可以選擇使用下列任何一種組合封存資料庫：
  
- 監控資料庫
    
- Enterprise Edition 前端集區的後端資料庫
    
> [!NOTE]
> 裝載封存資料庫的伺服器可以裝載其他資料庫。不過，當您考慮將封存資料庫與其他資料庫組合時，請注意，如果您要封存較多使用者的訊息，封存資料庫所需的磁碟空間可能會變得極大。基於這項因素，建議您不要將封存資料庫與後端資料庫整合。 
  
如果您組合封存資料庫與監控資料庫、後端資料庫或這兩種資料庫，您可以針對任何或所有資料庫使用單一 SQL 實例，也可以針對每個資料庫使用個別的 SQL 實例，但有下列限制：每個 SQL 實例僅可包含單一後端資料庫。 單一監控資料庫和單一封存資料庫。
  
如需組合所有伺服器角色及資料庫的詳細資訊，請參閱[拓撲基礎的商務用 Skype Server](../../plan-your-deployment/topology-basics/topology-basics.md)。 如需更新拓撲以包含儲存資料庫的詳細資訊，請參閱[Create and publish new 拓朴 in 商務用 Skype Server](../../deploy/install/create-and-publish-new-topology.md)。
  
### <a name="determine-archiving-options-and-user-policies"></a>決定封存選項和使用者原則

您將需要判斷：
  
- 是否要啟用或停用內部和外部通訊的封存
    
- 是否要封存 IM、會議或兩者
    
- 是否要執行關鍵模式，以在商務用 Skype Server 失敗時封鎖 IM 和會議會話 
    
- 是否要啟用特定使用者和群組的原則
    
商務用 Skype Server您可以在下列層級指定封存選項。 
  
- **Global level 選項**。 這是預設的封存設定，適用于整個部署。 它會在您部署商務用 Skype Server 時建立，而且預設會停用內部和外部通訊的封存。 您無法刪除此選項。 如果您選擇 [刪除] 選項，全域選項會重設為預設設定。
    
- **網站層級選項**。 您可以建立及設定網站的網站層級封存選項，來啟用或停用一或多個特定網站的封存。 您可以刪除任何您建立的網站層級封存選項。 網站層級的封存選項會覆寫全域選項，但只適用于選項中所指定的網站。 
    
    例如，如果您為全域設定中的內部和外部通訊啟用封存，並建立在其中停用外部通訊封存的網站設定，則只會針對該網站封存內部通訊。 在另一個範例中，如果您只為全域設定中的 IM 啟用封存，並建立啟用 IM 和會議的封存的網站設定，則只會封存該網站的會議，而不會為組織的其餘部分封存會議。
    
- **集區層級選項**。 您可以建立及設定個別集區的集區層級設定，以指定一或多個特定集區的封存設定。 集區層級的封存設定只有在您建立時才會存在。 您可以修改和刪除任何集區層級的封存設定。 集區層級的封存設定會覆寫全域設定和您已建立的任何網站封存設定。 
    
    例如，假設您只會在全域設定中啟用 IM 的封存功能，然後建立網站層級設定，讓您啟用 IM 和會議的封存，然後建立集區層級設定，讓您只啟用 IM 的封存。 除了集區層級設定所指定集區中的使用者之外，還會針對網站的所有使用者封存 IM 和會議的通訊。 組織中的所有其他使用者都只會啟用 IM 的封存。
    
- **使用者封存原則**。 您可以為指定的使用者和使用者群組建立、設定及套用使用者層級的封存原則，以啟用或停用一或多個特定使用者和使用者群組的封存。 您可以刪除任何您建立的使用者層級封存原則，也可以變更封存原則所套用的使用者和使用者群組。 使用者層級的封存原則會覆寫全域原則及任何網站原則，但僅限於套用該原則的使用者和使用者群組。 
    
    例如，假設您為全域設定中的內部和外部通訊停用封存，請建立網站層級原則，以啟用內部和外部通訊的封存，然後建立使用者層級原則，以停用封存以進行外部通訊。 除了套用使用者層級原則的使用者之外，所有網站使用者的外部和內部通訊都會封存通訊，但只會封存這些使用者的內部通訊。
    
如需如何在部署封存時設定初始封存設定的詳細資訊，請參閱[部署商務用 Skype Server 的](../../deploy/deploy-archiving/deploy-archiving.md)封存。 如需在部署後管理封存的詳細資訊，請參閱[Manage 封存 in 商務用 Skype Server](../../manage/archiving/archiving.md)。 
  
## <a name="archiving-configuration-tools"></a>封存組態工具

 您可以使用商務用 Skype Server 控制台控制大部分的封存選項。 不過，只有使用商務用 Skype Server 管理命令介面時，有一些選項可供使用。 這些選項包括封存重複郵件和匯出封存的資料。 如需使用商務用 Skype Server 控制台和商務用 Skype Server 管理命令介面來管理封存原則的詳細資訊，請參閱[manage 封存 in 商務用 Skype Server](../../manage/archiving/archiving.md)。
  
## <a name="access-archived-data"></a>存取封存的資料

存取封存的資料會根據儲存資料的地方而定： 
  
- **Microsoft Exchange 儲存空間**。 如果您選擇 Exchange 的整合選項，請商務用 Skype Server 在 Exchange 存放區中為位於 Exchange 上的所有使用者，以及其信箱置於 In-Place 保留狀態的情況下，將其存款。 封存的資料儲存在「可復原的使用者信箱」資料夾中（通常是使用者看不到），而且只能由具有 Exchange **探索管理** 角色的使用者來搜尋。 Exchange 會在部署時啟用同盟搜尋與探索，以及 SharePoint。 如需儲存在 Exchange 中之資料儲存、保留及探索的詳細資訊，請參閱 Exchange 和 SharePoint 檔。
    
- 封存 **儲存區商務用 Skype Server**。 如果您設定商務用 Skype Server 封存資料庫，商務用 Skype Server 在商務用 Skype Server 封存資料庫中對不是位於 Exchange 的任何使用者儲蓄內容，而且未將其信箱置於 In-Place 保留狀態。 此資料是無法搜尋的，但可匯出為可使用其他工具搜尋的格式。 如需匯出儲存在封存資料庫中之資料的詳細資訊，請參閱[在商務用 Skype Server 中匯出封存的資料](../../manage/archiving/export-archived-data.md)。
    
## <a name="for-more-information"></a>相關資訊

如需有關封存的詳細資訊，請參閱下列主題：
  
- [部署商務用 Skype Server 的封存](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [管理商務用 Skype Server 中的封存](../../manage/archiving/archiving.md)
    
如需商務用 Skype Server 和 Exchange 共同運作方式的詳細資訊，請參閱[Plan to 整合商務用 Skype 和 Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。
  

