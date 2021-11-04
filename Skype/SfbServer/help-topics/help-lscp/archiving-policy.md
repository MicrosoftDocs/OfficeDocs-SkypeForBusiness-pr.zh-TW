---
title: 封存原則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: 您可以使用封存原則來啟用及停用商務用 Skype Server 中使用者的封存。 在每個封存原則中，您可以啟用或停用下列其中一項或兩項的封存：
ms.openlocfilehash: 37452d6bc5274aad19508522bef60ec23e363fe4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60757535"
---
# <a name="archiving-policy"></a>封存原則
 
您可以使用封存原則來啟用及停用商務用 Skype Server 中使用者的封存。 在每個封存原則中，您可以啟用或停用下列其中一項或兩項的封存：
  
- 內部通訊
    
- 在內部網路以外至少包含一位使用者的外部通訊 (通訊) 
    
封存原則包含全域原則，並選擇性地包含一或多個網站與使用者封存原則：
  
- **全域原則** 預設會在所有部署中建立全域原則。 您可以編輯全域原則，但無法刪除此原則。 若嘗試將其刪除，所有選項都會重設為預設值。
    
- **網站原則 (選用)** 您可以指定一或多個網站封存原則，每個網站封存原則都可以設定為啟用和停用單一網站的內部或外部通訊的封存。 網站原則會覆寫全域原則，但僅限於您的封存網站原則中所指定的網站。 您可以編輯或刪除網站原則。
    
- **使用者原則 (選用)** 您可以指定一或多個使用者封存原則，每個使用者封存原則都可以設定為啟用及停用特定使用者或使用者群組的內部或外部通訊的封存。 使用者原則會覆寫全域原則及網站原則，但僅限於您指派使用者層級封存原則的使用者和使用者群組。 您可以編輯或刪除使用者原則。
    
> [!NOTE]
> 封存原則只適用于位於商務用 Skype Server 上的使用者。 如果您使用 Exchange 整合將封存資料儲存在 Microsoft Exchange 中，則 Exchange 2013 原則會控制位於 Exchange 2013 上之使用者的封存。 若要為這些使用者啟用封存，使用者的信箱必須置於 In-Place 保留狀態。 
  
「封存 **原則** 」頁面會列出為您的部署設定的每個封存原則。 它也會顯示原則名稱、範圍 (全域、網站或使用者) ，以及針對每個封存原則啟用的封存選項。 在 [封存 **原則** ] 頁面上，您可以使用下列選項：
- **新** 您可以新增一或多個下列選用的封存原則：
    
  - 網站原則
    
  - 使用者原則
    
- **編輯** 您可以變更頁面上所列之任何封存原則的選項。 使用此選項，您可以執行下列作業：
    
  - **顯示詳細資料** 此選項會開啟一個對話方塊，您可以在其中變更封存原則的封存選項。
    
  - **全選** 此選項會選取清單中的所有封存原則。
    
  - **Delete** 此選項會刪除所有選取的封存原則。
    
- **動作** 您可以使用此選項，在頁面上所列的任何原則中快速啟用或停用內部或外部通訊的封存，而不是編輯原則。 [ **動作** ] 下的可用選項取決於封存原則中目前指定的選項。 所有選項均可使用，但目前對封存原則有效的選項除外。 選項包括下列各項：
    
  - **啟用內部通訊的封存**
    
  - **停用內部通訊的封存**
    
  - **啟用外部通訊的封存**
    
  - **停用外部通訊的封存**
    
- **Refresh** 您可以重新整理「封存 **原則** 」頁面，以確認所有封存原則選項的狀態。
    
如需封存功能及功能的詳細資料，包括 Exchange 整合，請參閱[在商務用 Skype Server 2015 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 Skype Server 2015 的](../../deploy/deploy-archiving/deploy-archiving.md)封存，以及[管理商務用 Skype Server 2015 中](../../manage/archiving/archiving.md)的封存。

