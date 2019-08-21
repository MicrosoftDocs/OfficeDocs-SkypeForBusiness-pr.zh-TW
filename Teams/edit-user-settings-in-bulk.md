---
title: 大量編輯 Microsoft 團隊使用者設定
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何大量在 Microsoft 團隊系統管理中心管理 Microsoft 團隊使用者設定。
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c57ae4978e0cfacf69c9e68fb47d3f28ad5c4f4d
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483745"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="96985-103">大量編輯 Microsoft 團隊使用者設定</span><span class="sxs-lookup"><span data-stu-id="96985-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="96985-104">做為管理員, 您可以在 Microsoft 團隊系統管理中心管理團隊使用者設定。</span><span class="sxs-lookup"><span data-stu-id="96985-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="96985-105">在 [**使用者**] 頁面上, 您可以查看相關資訊, 例如帳戶和授權詳細資料, 以及編輯原則及其他設定。</span><span class="sxs-lookup"><span data-stu-id="96985-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="96985-106">您可以個別或多位使用者編輯使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="96985-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="96985-107">大量編輯使用者設定</span><span class="sxs-lookup"><span data-stu-id="96985-107">Edit user settings in bulk</span></span>

<span data-ttu-id="96985-108">使用 Microsoft 團隊系統管理中心來一次編輯多位使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="96985-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="96985-109">我們建議您一次編輯20個使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="96985-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="96985-110">若要編輯大量使用者的設定, 請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96985-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="96985-111">如需詳細資訊, 請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="96985-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="96985-112">在 Microsoft [團隊管理中心] 的左導覽中, 選取 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="96985-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="96985-113">搜尋您要編輯的使用者, 或篩選該視圖, 以顯示您要編輯的使用者。</span><span class="sxs-lookup"><span data-stu-id="96985-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="96985-114">在 [ **&#x2713;** (核取符號)] 欄中, 執行下列其中一項動作來選取 [使用者]:</span><span class="sxs-lookup"><span data-stu-id="96985-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="96985-115">一次選取一個使用者。</span><span class="sxs-lookup"><span data-stu-id="96985-115">Select users one at a time.</span></span> <span data-ttu-id="96985-116">您所選取的每位使用者旁邊都會顯示 **&#x2713;** 。</span><span class="sxs-lookup"><span data-stu-id="96985-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="96985-117">如果您選取超過20個使用者, 將不會封鎖您, 但請記住, 您選取的使用者越多, 就會花更長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="96985-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![顯示使用者選取範圍之 [使用者] 頁面的螢幕擷取畫面](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="96985-119">按一下表格頂端的 [&#x2713; (核取標記) 來選取 [所有使用者 (最多20個使用者)], 然後在 [**選取範圍限制**] 對話方塊中, 按一下 [**繼續選取 [全部**] 以完成選取專案。</span><span class="sxs-lookup"><span data-stu-id="96985-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="96985-120">![顯示選取範圍限制的 [使用者] 頁面螢幕擷取畫面](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="96985-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="96985-121">選取的使用者旁邊會顯示 **&#x2713;** 。</span><span class="sxs-lookup"><span data-stu-id="96985-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![[使用者] 頁面的螢幕擷取畫面, 顯示已選取20個使用者](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="96985-123">按一下 [**編輯設定**], 進行您想要的變更, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="96985-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![[編輯設定] 窗格的螢幕擷取畫面](media/bulk-edit-user-settings-edit-settings.png)
