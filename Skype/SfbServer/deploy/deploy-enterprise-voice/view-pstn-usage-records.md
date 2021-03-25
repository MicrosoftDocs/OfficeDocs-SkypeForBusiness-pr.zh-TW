---
title: 在商務用 Skype 中查看 PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：瞭解如何使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來查看 PSTN 使用方式記錄。
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109829"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="e53a0-103">在商務用 Skype 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="e53a0-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="e53a0-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來查看 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="e53a0-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="e53a0-105">公用交換電話網路 (PSTN) 使用方式記錄會指定呼叫類別 (例如內部、本機或長途) ，可由組織中的各種使用者或使用者群組進行。</span><span class="sxs-lookup"><span data-stu-id="e53a0-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="e53a0-106">如需詳細資訊，請參閱規劃文件中的 [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)。</span><span class="sxs-lookup"><span data-stu-id="e53a0-106">For details, see [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e53a0-107">使用商務用 Skype Server 控制台來查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="e53a0-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e53a0-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e53a0-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="e53a0-109">在左導覽列中，按一下 **[語音路由]**，然後按一下 **[PSTN 使用方式]**。</span><span class="sxs-lookup"><span data-stu-id="e53a0-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="e53a0-110">在 **[PSTN 使用方式]** 頁面上，反白想要檢視的 PSTN 使用方式記錄，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="e53a0-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e53a0-111">所選取 PSTN 使用方式記錄的唯讀頁面顯示相關聯的路由及相關聯的語音原則。</span><span class="sxs-lookup"><span data-stu-id="e53a0-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="e53a0-112">使用商務用 Skype Server 管理命令介面 Cmdlet 來查看 PSTN 使用狀況資訊</span><span class="sxs-lookup"><span data-stu-id="e53a0-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="e53a0-113">若要查看所有 PSTN 使用方式的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="e53a0-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="e53a0-114">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="e53a0-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="e53a0-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e53a0-115">See also</span></span>

[<span data-ttu-id="e53a0-116">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="e53a0-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)