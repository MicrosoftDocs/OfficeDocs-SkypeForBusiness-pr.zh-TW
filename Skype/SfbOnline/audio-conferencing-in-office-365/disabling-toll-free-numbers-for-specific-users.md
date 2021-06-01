---
title: 停用特定線上使用者的免付費商務用 Skype號碼
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
description: 系統管理員可以控制召集人如何為會議使用免付費號碼。
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238508"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="0dba4-103">停用特定線上使用者的免付費商務用 Skype號碼</span><span class="sxs-lookup"><span data-stu-id="0dba4-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="0dba4-104">有關停用使用者免Teams號碼的資訊，請參閱停用特定使用者的免付費[Teams號碼](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="0dba4-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="0dba4-105">如果貴組織在其 Microsoft 音訊會議橋接器中擁有免付費號碼，您可以允許或禁止在特定的召集人會議中使用。</span><span class="sxs-lookup"><span data-stu-id="0dba4-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="0dba4-106">根據預設，貴組織的所有使用者都可以使用免付費號碼，也就是說，參與者可以使用這些號碼來加入他們的會議 。如果可用的話，這些號碼可供參與者使用。</span><span class="sxs-lookup"><span data-stu-id="0dba4-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="0dba4-107">如果貴組織中某些使用者不是想要的行為，您可以透過免付費號碼啟用控制項，限制特定使用者在會議中使用這些號碼。</span><span class="sxs-lookup"><span data-stu-id="0dba4-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="0dba4-108">當為給定的召集人停用免付費號碼時：</span><span class="sxs-lookup"><span data-stu-id="0dba4-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="0dba4-109">免付費號碼將不再包含在其會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="0dba4-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="0dba4-110">免付費號碼將不再列在其會議邀請中參照的「尋找當地號碼」頁面上。</span><span class="sxs-lookup"><span data-stu-id="0dba4-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="0dba4-111">如果參與者撥打組織的任何免付費號碼，他們將無法加入該召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="0dba4-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="0dba4-112">召集人的所有會議都會自動重新排期，免付費號碼也會從它們中移除。</span><span class="sxs-lookup"><span data-stu-id="0dba4-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="0dba4-113">這會將召集人的所有電子郵件邀請重新發回給所有會議參與者。</span><span class="sxs-lookup"><span data-stu-id="0dba4-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="0dba4-114">參與者可以使用付費號碼繼續加入召集人的會議。</span><span class="sxs-lookup"><span data-stu-id="0dba4-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="0dba4-115">停用特定使用者的免付費電話號碼</span><span class="sxs-lookup"><span data-stu-id="0dba4-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="0dba4-116">從 Microsoft Teams **系統管理中心**：</span><span class="sxs-lookup"><span data-stu-id="0dba4-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="0dba4-117">在左側導覽中， **按一下 [使用者**，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="0dba4-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0dba4-118">在 [ **音訊會議」 旁**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="0dba4-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="0dba4-119">將 **此使用者的會議要求包含** 免付費號碼設定為 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="0dba4-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="0dba4-120">按一下 **[儲存。**</span><span class="sxs-lookup"><span data-stu-id="0dba4-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="0dba4-121">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0dba4-121">**Using PowerShell**</span></span>  

<span data-ttu-id="0dba4-122">您可以使用 Cmdlet 的 AllowTollFreeDialIn 參數Set-CsOnlineDialInConferencingUser啟用或停用此控制項。</span><span class="sxs-lookup"><span data-stu-id="0dba4-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="0dba4-123">例如：</span><span class="sxs-lookup"><span data-stu-id="0dba4-123">For example:</span></span> 

- <span data-ttu-id="0dba4-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="0dba4-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
