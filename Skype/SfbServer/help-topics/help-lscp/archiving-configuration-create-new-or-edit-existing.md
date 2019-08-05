---
title: 封存配置建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
description: 您可以使用封存組態控制部署的封存選項。封存組態除了包含全域組態之外，也可能包含一或多個站台組態與集區組態：
ms.openlocfilehash: d40750069d34cb274342c1f5aab5d8191f90a334
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193163"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>封存組態：建立新的或編輯現有
 
您可以使用封存組態控制部署的封存選項。封存組態除了包含全域組態之外，也可能包含一或多個站台組態與集區組態：
  
- **全域配置**預設會建立全域配置。 您可以編輯全域組態，但無法刪除該封存組態。 若您嘗試刪除，所有選項都會重設為預設值。
    
- **網站設定 (選用)** 您可以指定一個或多個網站歸檔設定, 每個設定都可以設定以控制特定網站的封存選項。 網站組態會覆寫全域組態，但僅限於該封存網站組態中指定的網站。 您可以編輯或刪除網站組態。
    
- **池配置 (選用)** 您可以指定一個或多個池存檔設定, 以控制特定池的存檔選項。 集區組態會覆寫全域組態及網站組態，但僅限於在封存集區組態中指定的集區。 您可以編輯或刪除集區組態。
    
> [!NOTE]
> 封存設定適用于駐留在商務用 Skype Server 的使用者, 如果您啟用 Microsoft Exchange 整合選項, 就能使用 Exchange 2013 來儲存 Microsoft Exchange 中的存檔資料, 給駐留在 Exchange 2013 的使用者。 不過, 對於駐留在 Exchange 2013 的使用者來說, 某些選項的執行方式稍有不同, 如下一節所述。 
  
若要設定現有或新的封存組態，請指定下列選項：
- **名稱**每個存檔設定都需要名稱。 名稱是由您要新增或編輯的配置類型決定:
    
  - **全域配置**預設名稱為全域。 例如，Contoso 北美組織。
    
  - **網站**設定清單包含您部署中可用的網站。 按一下某個網站加以選取。 例如，Redmond 資料中心。
    
  - **池配置**指定適當的名稱, 這可以是您部署中特定前端池或標準版伺服器的名稱。 例如：行銷部門。
    
- **描述**這是選擇性的。 使用它來提供其他詳細資料, 例如設定的範圍或用途。 例如, 與其他網站的法律部門共同合作。
    
- **存檔設定**選項包括下列各項:
    
  - **封存 IM 工作階段**
    
  - **封存 IM 與 Web 會議工作階段**
    
  - **停用封存**
    
- **如果存檔失敗, 封鎖立即訊息 (IM) 或網路會議會話**失敗包括下列各項:
    
  - **IM**失敗可能是儲存空間服務的完整資料庫或問題。 在此情況下，具有封存能力的使用者皆無法使用 IM。
    
  - **會議**失敗可能是無法使用的檔案共用或儲存服務的問題。 在此情況下，所有於失敗時間在集區中進行的會議，都會切換為限制模式，而且無法啟動新的會議。
    
    IM 和會議會在更正失敗之後自動復原。
    
- **Microsoft Exchange 整合**如果您擁有託管于 Exchange 2013 的使用者, 請選取此選項。 使用此選項時, 如果已將使用者的信箱放在適當的位置, Exchange 2013 會用來儲存這些使用者的資料。 如果您的所有使用者都是以 Exchange 2013 為宿主, 您就不需要設定個別的 SQL Server 資料庫來儲存存檔資料。
    
- **允許清除封存資料**選取此選項可啟用清除及指定清除選項, 包括下列各項:
    
  - 在指定的特定天數之後清除。
    
  - 在匯出封存資料之後進行清除 (包含已上傳至 Exchange 的資料, 如果您啟用 Microsoft Exchange 整合)。
    
    > [!NOTE]
    > 如果您啟用 Microsoft Exchange 整合, 請清除駐留在 Exchange 2013 的使用者, 並將其信箱放在就地保留中的使用者受到 Exchange 控制。 唯一的例外狀況是儲存在 Lync Server 檔案共用的會議檔案。 這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。 
  
如需有關存檔功能和功能 (包括 Exchange 整合) 的詳細資料, 請參閱[在商務用 Skype server 2015 中進行](../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server 2015 的](../../deploy/deploy-archiving/deploy-archiving.md)封存, 以及[在 Skype 中管理存檔商務伺服器 2015](../../manage/archiving/archiving.md)。

