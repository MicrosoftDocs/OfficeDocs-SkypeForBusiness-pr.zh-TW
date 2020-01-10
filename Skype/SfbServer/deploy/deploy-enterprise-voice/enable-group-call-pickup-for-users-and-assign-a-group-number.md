---
title: 在商務用 Skype 中為使用者啟用群組呼叫挑選並指派群組號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 在商務用 Skype Server Enterprise Voice 中啟用群組呼叫挑選的使用者，並指派群組號碼。
ms.openlocfilehash: 8ded9fbf7e9a9c8034684c1477c6aad92bfc9e5f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002543"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a><span data-ttu-id="fe980-103">在商務用 Skype 中為使用者啟用群組呼叫挑選並指派群組號碼</span><span class="sxs-lookup"><span data-stu-id="fe980-103">Enable Group Call Pickup for users and assign a group number in Skype for Business</span></span>

<span data-ttu-id="fe980-104">在商務用 Skype Server Enterprise Voice 中啟用群組呼叫挑選的使用者，並指派群組號碼。</span><span class="sxs-lookup"><span data-stu-id="fe980-104">Enable users for Group Call Pickup in Skype for Business Server Enterprise Voice, and assign a group number.</span></span>

<span data-ttu-id="fe980-105">在您將呼叫挑選群組編號新增至 [通話駐留軌道] 表格之後，您可以使用 SEFAUtil 工具，將群組號碼指派給使用者，並為他們啟用群組呼叫分揀。</span><span class="sxs-lookup"><span data-stu-id="fe980-105">After you add call pickup group numbers to the call park orbit table, you use the SEFAUtil tool to assign the group numbers to users and enable Group Call Pickup for them.</span></span>

> [!NOTE]
> <span data-ttu-id="fe980-106">在混合式部署中，請勿將群組呼叫挑選群組指派給駐留在線上的使用者。</span><span class="sxs-lookup"><span data-stu-id="fe980-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="fe980-107">以線上為宿主的使用者無法參與群組通話挑選。</span><span class="sxs-lookup"><span data-stu-id="fe980-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="fe980-108">也就是說，其他使用者無法接聽其來電，也無法將來電應答給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="fe980-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="fe980-109">指派群組號碼並為使用者啟用群組呼叫分揀</span><span class="sxs-lookup"><span data-stu-id="fe980-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1. <span data-ttu-id="fe980-110">以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="fe980-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2. <span data-ttu-id="fe980-111">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="fe980-111">At the command line, run:</span></span>

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    <span data-ttu-id="fe980-112">例如，若要將群組號碼199指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="fe980-112">For example, to assign group number 199 to a user:</span></span>

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a><span data-ttu-id="fe980-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fe980-113">See also</span></span>

[<span data-ttu-id="fe980-114">停用群組拾取給使用者</span><span class="sxs-lookup"><span data-stu-id="fe980-114">Disable Group Pickup for Users</span></span>](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

