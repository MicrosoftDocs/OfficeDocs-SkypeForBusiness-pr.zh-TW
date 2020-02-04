---
title: 存檔原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以在部署中，針對駐留在商務用 Skype Server 上的使用者，使用封存原則來控制內部與外部通訊的存檔。 封存原則包含全域原則，以及一或多個網站與使用者原則 (後者並非必要)：
ms.openlocfilehash: 1eb1f0060e80fbb7d325f5fbe1b7a247d6d006b6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691217"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>封存原則：建立新的或編輯現有
 
您可以在部署中，針對駐留在商務用 Skype Server 上的使用者，使用封存原則來控制內部與外部通訊的存檔。 封存原則包含全域原則，以及一或多個網站與使用者原則 (後者並非必要)：
  
- **全域原則**預設會在所有商務用 Skype Server 部署中建立全域原則。 您可以編輯全域原則，但無法刪除此原則。 如果嘗試刪除此原則，所有選項都會重設為預設值。
    
- **網站原則（選用）** 您可以指定一或多個網站封存策略，每個原則都可以設定為啟用和停用特定網站的內部或外部通訊的歸檔。 網站原則會覆寫全域原則，但僅限於封存原則中指定的網站。 您可以編輯或刪除網站原則。
    
- **使用者原則（選用）** 您可以指定一或多個使用者存檔原則，每個策略都可以設定為啟用和停用針對特定使用者進行內部或外部通訊的封存。 使用者原則會覆寫全域原則及網站原則，但僅限於獲得您指派使用者原則的使用者。 您可以編輯或刪除使用者原則。
    
> [!NOTE]
> 如果您使用 Exchange 整合來儲存 Microsoft Exchange 中的存檔資料，則 Exchange 原則會控制駐留在 Exchange 的使用者的封存。 若要為這些使用者啟用存檔，使用者的信箱必須放在就地保留中。 
  
若要設定新的或現有的封存原則設定，可指定下列選項：
- **名稱**每個存檔原則都需要一個名稱。 名稱是由您要新增或編輯的原則類型決定：
    
  - **全域原則**預設名稱為全域。 您可以將名稱改為更具描述性的名稱。 例如，Contoso 北美組織。
    
  - **網站原則**此對話方塊中所列的網站包含您部署中所有可用的網站。 按一下某個網站加以選取。 例如，Redmond 資料中心。
    
  - **使用者原則**指定適當的名稱，例如特定使用者的名稱，或貴組織中的使用者群組或團隊名稱。 例如，法務部門。
    
- **描述**這是選擇性的。 使用它來提供其他詳細資料，例如原則的範圍或用途。 例如，與其他網站的法律部門共同合作。
    
- 封存**內部通訊**選取此核取方塊以啟用內部網路上的通訊封存。 根據預設，在任何原則中都不會啟用這項功能。
    
- 封存**外部通訊**選取此核取方塊以啟用包含外部使用者（例如遠端使用者（包括匿名和 PIC 設定使用者）及聯盟夥伴的通訊的封存。 根據預設，在任何原則中都不會啟用這項功能。
    
如需有關存檔功能和功能（包括 Exchange 整合）的詳細資料，請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 skype server](../../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及[管理商務用 skype 伺服器](../../../manage/archiving/archiving.md)的封存。

