---
title: 管理 Skype 會議室系統帳戶
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: 閱讀此主題以瞭解如何管理 Skype 的會議室系統帳戶。
ms.openlocfilehash: 2ae91a977a837e2b1b54db8d127551b5f53bb1a8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864450"
---
# <a name="manage-skype-room-system-accounts"></a>管理 Skype 會議室系統帳戶
 
閱讀此主題以瞭解如何管理 Skype 的會議室系統帳戶。 

> [!NOTE]
> Microsoft Teams 會議室不同的產品，具有不同的相依性和部署程式。 如需 Microsoft Teams 會議室的詳細資訊，請參閱 Microsoft Teams 會議室[管理綜述](/microsoftteams/rooms/rooms-manage)。
  
## <a name="move-the-skype-room-system-account-between-pools"></a>在集區之間移動 Skype 的會議室系統帳戶

如果您需要將 Skype 的會議室系統帳戶從一個商務用 Skype Server 集區移至另一個 (例如，在升級) 期間，請使用下列命令來移動 Skype 的會議室系統帳戶集區： 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a>停用商務用 Skype 服務的 Skype 會議室系統帳戶

如果您需要從商務用 Skype Server 集區上商務用 Skype 服務停用現有的 Skype 會議室系統帳戶，請使用下列命令來停用帳戶： 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a>選用：在 Active Directory 中建立 Skype 的會議室系統管理員群組

加入網域的每個 Skype 的會議室系統用戶端，都可以由具有 Skype 室系統裝置電腦上的本機系統管理員許可權的網域使用者完整管理。 因此，您可以在 Active Directory 中建立專屬管理員群組，並在設定新的 Skype 房間系統機器時，授與此群組的系統管理許可權。
