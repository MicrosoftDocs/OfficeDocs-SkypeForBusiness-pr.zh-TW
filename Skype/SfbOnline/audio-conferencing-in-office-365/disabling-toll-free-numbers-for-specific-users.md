---
title: 針對特定商務用 Skype Online 使用者停用免付費電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 系統管理員可以控制召集人如何在會議中使用免付費電話號碼。
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695678"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="f7867-103">針對特定商務用 Skype Online 使用者停用免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="f7867-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>
 
> [!Note]
> <span data-ttu-id="f7867-104">如需針對團隊使用者停用免工具號碼的相關資訊，請參閱針對[特定團隊使用者停用免費電話號碼](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="f7867-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="f7867-105">如果您的組織在其 Microsoft 音訊會議橋中有免付費電話號碼，您可以在特定召集人的會議中允許或避免使用。</span><span class="sxs-lookup"><span data-stu-id="f7867-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="f7867-106">根據預設，貴組織中的所有使用者都可以使用免付費電話號碼，這表示這些號碼（如果有的話）可供參與者加入其會議。</span><span class="sxs-lookup"><span data-stu-id="f7867-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="f7867-107">如果這不是貴組織中的部分使用者所需的行為，您可以透過免付費號碼啟用控制，限制特定使用者在會議中使用這些號碼。</span><span class="sxs-lookup"><span data-stu-id="f7867-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="f7867-108">針對指定的召集人停用免付費電話號碼時：</span><span class="sxs-lookup"><span data-stu-id="f7867-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="f7867-109">免付費電話號碼將不再包含在他或她的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="f7867-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f7867-110">免付費電話號碼將不再列在他或她的會議邀請中所參照的 [尋找當地電話號碼] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f7867-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="f7867-111">如果您的召集人撥打任何免付費電話號碼，參與者將無法加入指定召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="f7867-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="f7867-112">召集人的所有會議都會自動重新安排，且免付費電話號碼將會從他們中移除。</span><span class="sxs-lookup"><span data-stu-id="f7867-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="f7867-113">這會將召集人的所有電子郵件邀請重新傳送給這些會議的所有參與者。</span><span class="sxs-lookup"><span data-stu-id="f7867-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="f7867-114">參與者可以使用電話號碼繼續加入召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="f7867-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="f7867-115">停用特定使用者的免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="f7867-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="f7867-116">從**Microsoft [團隊管理中心**]：</span><span class="sxs-lookup"><span data-stu-id="f7867-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="f7867-117">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="f7867-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f7867-118">按一下 [**音訊會議**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f7867-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="f7867-119">[設定] 會將**此使用者的會議邀請中的免付費電話號碼**設為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f7867-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="f7867-120">按一下 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="f7867-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="f7867-121">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f7867-121">**Using PowerShell**</span></span>  

<span data-ttu-id="f7867-122">您可以使用 Get-csonlinedialinconferencinguser Cmdlet 的 AllowTollFreeDialIn 參數來啟用或停用此控制項。</span><span class="sxs-lookup"><span data-stu-id="f7867-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="f7867-123">例如：</span><span class="sxs-lookup"><span data-stu-id="f7867-123">For example:</span></span> 

- <span data-ttu-id="f7867-124">Set-Get-csonlinedialinconferencinguser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="f7867-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
