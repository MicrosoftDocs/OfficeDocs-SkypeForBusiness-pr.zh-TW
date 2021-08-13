---
title: 封存設定建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用封存設定來控制部署的封存選項。 封存組態除了包含全域設定之外，也可能包含一或多個網站設定與集區設定：
ms.openlocfilehash: 74fc7795abdc97bc51404a88ef26cac3755d370a54e4b52fb53838cbd2fb11a6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325278"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>封存組態：建立新的或編輯現有
 
您可以使用封存設定來控制部署的封存選項。 封存組態除了包含全域設定之外，也可能包含一或多個網站設定與集區設定：
  
- **通用** 設定預設會建立全域設定。 您可以編輯全域設定，但無法刪除此封存組態。 若嘗試將其刪除，所有選項都會重設為預設值。
    
- **網站設定 (選用)** 您可以指定一或多個網站封存設定，每個網站封存設定可用於控制特定網站的封存選項。 網站設定會覆寫全域設定，但僅限於在封存網站設定中指定的網站。 您可以編輯或刪除網站設定。
    
- **集區設定 (選用)** 您可以指定一或多個集區封存設定，以控制特定集區的封存選項。 集區設定優先於全域設定與網站設定，但僅限於封存集區設定中所指定的集區。 您可以編輯或刪除集區設定。
    
> [!NOTE]
> 封存設定會套用至位於商務用 Skype Server 的使用者，而且，如果您啟用 microsoft Exchange 整合 Exchange 選項，將 microsoft Exchange 中的封存資料儲存在 Exchange 上的使用者。 不過，對於位於 Exchange 的使用者而言，有些選項的執行效果稍有不同，如下一節所述。 
  
若要設定現有或新的封存組態，請指定下列選項：
- **名稱** 每個封存設定都需要名稱。 其名稱取決於您要新增或編輯的設定類型：
    
  - **通用** 設定預設名稱為 Global。 例如：Contoso 北美組織。
    
  - **網站** 設定此清單包含您部署中可用的網站。 按一下某一個網站即可加以選取。 例如：Redmond 資料中心。
    
  - **集** 區設定指定適當的名稱，它可以是部署中特定前端集區的名稱或 Standard Edition 伺服器的名稱。 例如：行銷部門。
    
- **描述** 這是選用的。 使用它來提供其他詳細資料，例如設定的範圍或用法。 例如，與其他網站的法律部門進行協調。
    
- 封存 **設定** 選項包括下列各項：
    
  - **封存 IM 工作階段**
    
  - **封存 IM 和 Web 會議工作階段**
    
  - **停用封存**
    
- 封存 **失敗時封鎖立即訊息 (IM) 或 web 會議會話** 失敗包括下列各項：
    
  - **IM** 失敗可能是完整的資料庫或儲存服務的問題。 在此情況下，所有具有封存能力的使用者皆會無法使用 IM。
    
  - **會議** 失敗可能是無法使用的檔案共用或儲存服務的問題。 在此情況下，所有失敗時於集區中進行的會議，都會切換為限制模式，而且無法發起新的會議。
    
    IM 和會議會在失敗更正後自動復原。
    
- **Microsoft Exchange 整合** 如果您擁有位於 Exchange 的使用者，請選取此選項。 使用此選項時，如果使用者的信箱處於 In-Place 保留狀態，Exchange 會用來儲存這些使用者的資料。 如果您的所有使用者都位於 Exchange，您不需要設定個別的 SQL Server 資料庫來儲存封存資料。
    
- **啟用封存資料的清除** 選取此選項可啟用清除並指定清除選項，包括下列專案：
    
  - 在指定的特定天數之後清除。
    
  - 在匯出封存資料之後清除 (包括已上傳至 Exchange 的資料，如果您啟用 Microsoft Exchange 整合) 。
    
    > [!NOTE]
    > 如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 上的使用者，並將其信箱置於 In-Place 保留狀態，由 Exchange 所控制。 唯一的例外狀況是儲存在 Lync Server 檔共用上的會議檔案。 這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。 
  
如需封存功能及功能的詳細資料，包括 Exchange 整合，請參閱[在商務用 Skype Server 中規劃](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 Skype Server 的](../../../deploy/deploy-archiving/deploy-archiving.md)封存，以及[管理商務用 Skype Server 中](../../../manage/archiving/archiving.md)的封存。

