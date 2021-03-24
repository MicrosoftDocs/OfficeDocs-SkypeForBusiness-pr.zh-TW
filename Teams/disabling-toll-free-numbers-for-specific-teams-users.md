---
title: 停用特定 Teams 使用者的免付費號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 瞭解如何控制召集人如何使用免付費號碼進行音訊會議橋接器會議。
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096343"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="9ac8d-103">停用特定 Teams 使用者的免付費號碼</span><span class="sxs-lookup"><span data-stu-id="9ac8d-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="9ac8d-104">如果貴組織在其 Microsoft 音訊會議橋接器中擁有免付費號碼，您可以允許或禁止在特定的召集人會議中使用。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="9ac8d-105">根據預設，貴組織的所有使用者都可以使用免付費號碼，也就是說，參與者可以使用這些號碼來加入他們的會議 。如果可用的話，這些號碼可供參與者使用。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="9ac8d-106">如果貴組織中某些使用者不是想要的行為，您可以透過免付費號碼啟用控制項，限制特定使用者在會議中使用這些號碼。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="9ac8d-107">當為給定的召集人停用免付費號碼時：</span><span class="sxs-lookup"><span data-stu-id="9ac8d-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="9ac8d-108">免付費號碼將不再包含在其會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="9ac8d-109">免付費號碼將不再列在其會議邀請中參照的「尋找當地號碼」頁面上。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="9ac8d-110">如果參與者撥打組織的任何免付費號碼，他們將無法加入該召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="9ac8d-111">召集人的所有會議都會自動重新排期，免付費號碼也會從這些會議中移除。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="9ac8d-112">這會將召集人的所有電子郵件邀請重新發回給這些會議的所有參與者。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="9ac8d-113">參與者可以使用付費號碼繼續加入召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="9ac8d-114">停用特定使用者的免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="9ac8d-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="9ac8d-115">從 **Microsoft Teams 系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="9ac8d-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="9ac8d-116">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9ac8d-117">在 [ **音訊會議」 旁**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="9ac8d-118">將 **此使用者的會議要求包含** 免付費號碼設定為 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="9ac8d-119">按一下 **[儲存。**</span><span class="sxs-lookup"><span data-stu-id="9ac8d-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="9ac8d-120">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9ac8d-120">**Using PowerShell**</span></span>  

<span data-ttu-id="9ac8d-121">請參閱 [Microsoft Teams PowerShell 參考以](/powershell/module/teams/?view=teams-ps) 瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="9ac8d-121">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>