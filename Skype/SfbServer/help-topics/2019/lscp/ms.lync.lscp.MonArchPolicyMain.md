---
title: 封存原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用 [封存原則] 來啟用和停用駐留在商務用 Skype Server 上的使用者的封存。 在每個封存原則中，您可以從下列項目擇一或兩者皆啟用或停用封存：
ms.openlocfilehash: bdeb7925256e47ac61d0210e1be36e28dbdfc0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192296"
---
# <a name="archiving-policy"></a>封存原則
 
您可以使用 [封存原則] 來啟用和停用駐留在商務用 Skype Server 上的使用者的封存。 在每個封存原則中，您可以從下列項目擇一或兩者皆啟用或停用封存：
  
- 內部通訊
    
- 外部通訊 (此通訊至少包含一位在您內部網路外的使用者)
    
封存原則包含全域原則以及選用的一或多個網站與使用者封存原則：
  
- **全域原則**全域原則預設是在所有部署中建立。 您可以編輯全域原則，但無法刪除此原則。 如果嘗試刪除此原則，所有選項都會重設為預設值。
    
- **網站原則 (選用)** 您可以指定一或多個網站封存策略, 每個原則都可以設定為啟用和停用單一網站的內部或外部通訊的歸檔。 網站原則將覆寫全域原則，但僅限於該封存網站原則中指定的網站。 您可以編輯或刪除網站原則。
    
- **使用者原則 (選用)** 您可以指定一或多個使用者存檔原則, 每個策略都可以設定為啟用和停用特定使用者或使用者群組的內部或外部通訊的歸檔。 使用者原則會覆寫全域原則及網站原則，但僅限於獲得您指派使用者等級封存原則的使用者及使用者群組。 您可以編輯或刪除使用者原則。
    
> [!NOTE]
> 存檔原則只適用于駐留在商務用 Skype Server 上的使用者。 如果您使用 Exchange 整合來儲存 Microsoft Exchange 中的存檔資料, 則 Exchange 原則會控制駐留在 Exchange 的使用者的封存。 若要為這些使用者啟用存檔, 使用者的信箱必須放在就地保留中。 
  
「封存原則」**** 頁面列出針對您部署所設定的每個封存原則。該頁面也會顯示原則名稱、範圍 (全域、網站或使用者)，以及已針對每個封存原則啟用的封存選項。您可從「封存原則」**** 頁面執行下列選項：
- **新增**您可以新增下列其中一或多個選用的存檔原則:
    
  - 網站原則
    
  - 使用者原則
    
- [**編輯**]您可以變更頁面上所列之任何存檔策略的選項。 使用此選項, 您可以執行下列動作:
    
  - **顯示詳細資料** 此選項會開啟對話方塊供您變更封存原則的封存選項。
    
  - **全選** 此選項會選取清單中的所有封存原則。
    
  - **刪除** 此選項會刪除所有選取的封存原則。
    
- **動作**您可以使用這個選項, 在頁面上所列的任何原則中快速啟用或停用內部或外部通訊的封存, 而不是編輯原則。 [**動作**] 底下的可用選項, 取決於 [存檔原則] 中目前指定的選項。 除了目前對存檔原則有效的選項之外, 所有選項皆可使用。 選項包括下列各項:
    
  - **啟用內部通訊的封存**
    
  - **停用內部通訊的封存**
    
  - **啟用外部通訊的封存**
    
  - **停用外部通訊的封存**
    
- **更新**您可以重新整理 [封存**原則**] 頁面, 驗證所有存檔原則的選項狀態。
    
如需有關存檔功能和功能 (包括 Exchange 整合) 的詳細資料, 請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務](../../../deploy/deploy-archiving/deploy-archiving.md)用 skype server 的封存, 以及[管理商務用 skype 中的封存伺服器](../../../manage/archiving/archiving.md)。

