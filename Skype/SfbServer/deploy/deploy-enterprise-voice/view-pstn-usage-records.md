---
title: 在商務用 Skype 中查看 PSTN 使用狀況記錄
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：瞭解如何使用商務用 Skype Server [控制台] 或商務用 Skype Server 管理命令介面來查看 PSTN 使用記錄。
ms.openlocfilehash: 96a96898bf728b4f05ba473bc750635e41be19fa
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002723"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="b34e1-103">在商務用 Skype 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="b34e1-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="b34e1-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來查看 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="b34e1-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="b34e1-105">公用交換電話網絡（PSTN）使用記錄會指定呼叫類別（例如內部、當地或長途），這些使用者可以由不同的使用者或組織中的使用者群組進行。</span><span class="sxs-lookup"><span data-stu-id="b34e1-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="b34e1-106">如需詳細資訊，請參閱規劃檔中的[PSTN 使用記錄](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b34e1-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b34e1-107">使用商務用 Skype Server [控制台] 來查看 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="b34e1-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b34e1-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b34e1-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="b34e1-109">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [ **PSTN 使用狀況**]。</span><span class="sxs-lookup"><span data-stu-id="b34e1-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="b34e1-110">在 [ **Pstn 使用狀況**] 頁面上，醒目提示您要查看的 PSTN 使用記錄，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b34e1-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b34e1-111">所選 PSTN 使用記錄的唯讀頁面會顯示關聯的路線及相關的語音原則。</span><span class="sxs-lookup"><span data-stu-id="b34e1-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="b34e1-112">使用商務用 Skype Server Management Shell Cmdlet 來查看 PSTN 使用狀況資訊</span><span class="sxs-lookup"><span data-stu-id="b34e1-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="b34e1-113">若要查看所有 PSTN 用法的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="b34e1-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```powershell
  Get-CsPstnUsage
  ```

    <span data-ttu-id="b34e1-114">這個命令會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="b34e1-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="b34e1-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b34e1-115">See also</span></span>

[<span data-ttu-id="b34e1-116">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="b34e1-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

