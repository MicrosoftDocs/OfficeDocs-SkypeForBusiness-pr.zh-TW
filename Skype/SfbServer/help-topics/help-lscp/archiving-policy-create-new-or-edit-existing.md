---
title: 封存原則建立新的或編輯現有
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
description: 您可以使用封存原則，針對位於商務用 Skype Server 的使用者，控制部署中內部和外部通訊的封存。 封存原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：
ms.openlocfilehash: a32ca25092c5240b3be2080098b8bd8bc3477ec6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838785"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>封存原則：建立新的或編輯現有原則
 
您可以使用封存原則，針對位於商務用 Skype Server 的使用者，控制部署中內部和外部通訊的封存。 封存原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：
  
- **全域原則** 預設會在所有的商務用 Skype Server 部署中建立全域原則。 您可以編輯全域原則，但無法刪除此原則。 若嘗試將其刪除，所有選項都會重設為預設值。
    
- **網站原則 (選用)** 您可以指定一或多個網站封存原則，每個網站封存原則都可以設定為啟用和停用特定網站的內部或外部通訊的封存。 網站原則會覆寫全域原則，但僅限於封存原則中指定的網站。 您可以編輯或刪除網站原則。
    
- **使用者原則 (選用)** 您可以指定一或多個使用者封存原則，每個使用者封存原則都可以設定為針對特定使用者，啟用和停用內部或外部通訊的封存。 使用者原則會覆寫全域原則及網站原則，但僅限於您指派使用者原則的使用者 (s) 。 您可以編輯或刪除使用者原則。
    
> [!NOTE]
> 如果您使用 Exchange 整合將封存資料儲存在 Microsoft Exchange 中，則 Exchange 2013 原則會控制位於 Exchange 2013 上之使用者的封存。 若要為這些使用者啟用封存，使用者的信箱必須置於 In-Place 保留狀態。 
  
若要設定新的或現有的封存原則設定，請指定下列選項：
- **名稱** 每個封存原則都需要一個名稱。 其名稱取決於您要新增或編輯的原則類型：
    
  - **全域原則** 預設名稱為 Global。 您可以將它變更為更具描述性的名稱。 例如：Contoso 北美組織。
    
  - **網站原則** 此對話方塊中所列的網站包含部署中所有可用的網站。 按一下某一個網站即可加以選取。 例如：Redmond 資料中心。
    
  - **使用者原則** 指定適當的名稱，例如特定使用者的名稱，或組織中使用者群組或小組的名稱。 例如法律部門。
    
- **描述** 這是選用的。 使用它來提供其他詳細資料，例如原則的範圍或用法。 例如，與其他網站的法律部門進行協調。
    
- 封存 **內部通訊** 選取此核取方塊以啟用內部網路上的通訊的封存。 根據預設，不會在任何原則中啟用此功能。
    
- 封存 **外部通訊** 選取此核取方塊可啟用包含外部使用者（例如遠端使用者）的通訊封存， (包括匿名和 PIC 使用者) 及同盟協力廠商。 根據預設，不會在任何原則中啟用此功能。
    
如需封存功能及功能的詳細資料，包括 Exchange 整合，請參閱[在商務用 Skype Server 2015 中規劃](../../plan-your-deployment/archiving/archiving.md)封存、[部署商務用 Skype Server 2015 的](../../deploy/deploy-archiving/deploy-archiving.md)封存，以及[管理商務用 Skype Server 2015 中](../../manage/archiving/archiving.md)的封存。

