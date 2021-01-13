---
title: 管理 Skype 會議室系統帳戶
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 閱讀此主題以瞭解如何管理 Skype 室系統帳戶。
ms.openlocfilehash: fe6438934fa8fffabbc73c96ac00fd7844b51e14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805553"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 會議室系統帳戶
 
閱讀此主題以瞭解如何管理 Skype 室系統帳戶。 

> [!NOTE]
> Microsoft 團隊聊天室是不同的產品，具有不同的相依性和部署程式。 如需 Microsoft 小組聊天室的詳細資訊，請參閱 Microsoft 團隊聊天室 [管理綜述](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在集區之間移動 Skype 室系統帳戶

如果您需要將商務用 skype 系統帳戶從一個 Skype Server 集區移至另一個 (例如，在升級期間) ，請使用下列命令來移動 Skype 室系統帳戶集區： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>停用商務用 Skype 服務的 Skype 室系統帳戶

如果您需要在商務用 skype 伺服器集區上從商務用 Skype 服務停用現有的 Skype 會議室系統帳戶，請使用下列命令來停用帳戶： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>選用：在 Active Directory 中建立 Skype 會議室系統管理員群組

加入網域的每一個 Skype 會議室系統用戶端，都可以由具有 Skype 室系統裝置電腦上的本機系統管理員許可權的網域使用者完整管理。 因此，您可以在 Active Directory 中建立專屬管理員群組，並在設定新的 Skype 會議室系統機器時，給予此群組的系統管理許可權。
  

