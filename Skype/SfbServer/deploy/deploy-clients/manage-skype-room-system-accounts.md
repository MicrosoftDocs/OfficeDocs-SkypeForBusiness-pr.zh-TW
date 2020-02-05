---
title: 管理 Skype 會議室系統帳戶
ms.author: v-lanac
author: lanachin
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
description: 若要瞭解如何管理 Skype 室系統帳戶，請閱讀本主題。
ms.openlocfilehash: b6d61f4ddc9fe5e296ffd98b685e1000151d5db2
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768656"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="cd04c-103">管理 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="cd04c-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="cd04c-104">若要瞭解如何管理 Skype 室系統帳戶，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="cd04c-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd04c-105">Microsoft 團隊聊天室是不同的產品，具有不同的相依性與部署程式。</span><span class="sxs-lookup"><span data-stu-id="cd04c-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="cd04c-106">如需 Microsoft 團隊聊天室的詳細資訊，請參閱 Microsoft 團隊聊天室[管理概覽](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage)。</span><span class="sxs-lookup"><span data-stu-id="cd04c-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](https://docs.microsoft.com/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="cd04c-107">在池之間移動 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="cd04c-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="cd04c-108">如果您需要將 Skype 會議室系統帳戶從一個商務用 Skype 伺服器池移至另一個（例如升級期間），請使用下列命令來移動 Skype 會議室系統帳戶池：</span><span class="sxs-lookup"><span data-stu-id="cd04c-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="cd04c-109">針對商務用 Skype 服務停用 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="cd04c-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="cd04c-110">如果您需要在商務用 Skype 伺服器池中停用商務用 Skype 服務的現有 Skype 會議室系統帳戶，請使用下列命令來停用帳戶：</span><span class="sxs-lookup"><span data-stu-id="cd04c-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="cd04c-111">選用：在 Active Directory 中建立 Skype 會議室系統管理員群組</span><span class="sxs-lookup"><span data-stu-id="cd04c-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="cd04c-112">加入網域的每個 Skype 會議室系統用戶端都可以由擁有 Skype 室系統裝置電腦上的本機系統管理員許可權的網域使用者來完全管理。</span><span class="sxs-lookup"><span data-stu-id="cd04c-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="cd04c-113">因此，您可以在 Active Directory 中建立專用的管理員群組，並在設定新的 Skype 會議室系統電腦時，給予這個群組的管理許可權。</span><span class="sxs-lookup"><span data-stu-id="cd04c-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

