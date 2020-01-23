---
title: 管理 Skype 會議室系統帳戶
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 若要瞭解如何管理 Skype 室系統帳戶，請閱讀本主題。
ms.openlocfilehash: d1cd40b12da89eed651152dd3b7b91914826d62e
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268469"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 會議室系統帳戶
 
若要瞭解如何管理 Skype 室系統帳戶，請閱讀本主題。 

> [!NOTE]
> Microsoft 團隊聊天室是不同的產品，具有不同的相依性與部署程式。 如需 Microsoft 團隊聊天室的詳細資訊，請參閱 Microsoft 團隊聊天室[管理概覽](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在池之間移動 Skype 會議室系統帳戶

如果您需要將 Skype 會議室系統帳戶從一個商務用 Skype 伺服器池移至另一個（例如升級期間），請使用下列命令來移動 Skype 會議室系統帳戶池： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>針對商務用 Skype 服務停用 Skype 會議室系統帳戶

如果您需要在商務用 Skype 伺服器池中停用商務用 Skype 服務的現有 Skype 會議室系統帳戶，請使用下列命令來停用帳戶： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>選用：在 Active Directory 中建立 Skype 會議室系統管理員群組

加入網域的每個 Skype 會議室系統用戶端都可以由擁有 Skype 室系統裝置電腦上的本機系統管理員許可權的網域使用者來完全管理。 因此，您可以在 Active Directory 中建立專用的管理員群組，並在設定新的 Skype 會議室系統電腦時，給予這個群組的管理許可權。
  

