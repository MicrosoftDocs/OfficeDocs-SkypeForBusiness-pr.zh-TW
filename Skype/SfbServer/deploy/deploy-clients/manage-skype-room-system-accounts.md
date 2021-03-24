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
ms.openlocfilehash: e6b905b065badb729ccc9281d63ba050fc032ef2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093291"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="7371e-103">管理 Skype 會議室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="7371e-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="7371e-104">閱讀此主題以瞭解如何管理 Skype 室系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="7371e-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="7371e-105">Microsoft 團隊聊天室是不同的產品，具有不同的相依性和部署程式。</span><span class="sxs-lookup"><span data-stu-id="7371e-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="7371e-106">如需 Microsoft 小組聊天室的詳細資訊，請參閱 Microsoft 團隊聊天室 [管理綜述](/microsoftteams/rooms/rooms-manage)。</span><span class="sxs-lookup"><span data-stu-id="7371e-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](/microsoftteams/rooms/rooms-manage).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="7371e-107">在集區之間移動 Skype 室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="7371e-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="7371e-108">如果您需要將商務用 skype 系統帳戶從一個 Skype Server 集區移至另一個 (例如，在升級期間) ，請使用下列命令來移動 Skype 室系統帳戶集區：</span><span class="sxs-lookup"><span data-stu-id="7371e-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```powershell
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="7371e-109">停用商務用 Skype 服務的 Skype 室系統帳戶</span><span class="sxs-lookup"><span data-stu-id="7371e-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="7371e-110">如果您需要在商務用 skype 伺服器集區上從商務用 Skype 服務停用現有的 Skype 會議室系統帳戶，請使用下列命令來停用帳戶：</span><span class="sxs-lookup"><span data-stu-id="7371e-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```powershell
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="7371e-111">選用：在 Active Directory 中建立 Skype 會議室系統管理員群組</span><span class="sxs-lookup"><span data-stu-id="7371e-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="7371e-112">加入網域的每一個 Skype 會議室系統用戶端，都可以由具有 Skype 室系統裝置電腦上的本機系統管理員許可權的網域使用者完整管理。</span><span class="sxs-lookup"><span data-stu-id="7371e-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="7371e-113">因此，您可以在 Active Directory 中建立專屬管理員群組，並在設定新的 Skype 會議室系統機器時，給予此群組的系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="7371e-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
