---
title: 設定邀請中包含的電話號碼
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 請按照下列步驟建立預設電話號碼，讓來電者加入 Microsoft Teams 會議。
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117171"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="831e5-103">在 Microsoft Teams 中設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="831e5-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="831e5-104">Microsoft 365 和 Office 365 的音訊會議可讓貴組織的使用者建立 Microsoft Teams 會議，然後允許使用者使用電話撥入這些會議。</span><span class="sxs-lookup"><span data-stu-id="831e5-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="831e5-105">會議橋接器會提供您組織的一組撥入電話號碼。</span><span class="sxs-lookup"><span data-stu-id="831e5-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="831e5-106">所有會議都可以用來加入會議召集人已建立的會議，但您可以選取哪些會議邀請會包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="831e5-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="831e5-107">會議邀請的會議召集人最多可以有一個付費電話和一個免付費電話號碼，但每個會議邀請底部也有一個連結，可開啟可用來加入會議之所有撥入電話號碼的完整清單。</span><span class="sxs-lookup"><span data-stu-id="831e5-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="831e5-108">新使用者會議邀請中包含的電話號碼初始指派</span><span class="sxs-lookup"><span data-stu-id="831e5-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="831e5-109">啟用音訊會議之使用者的會議邀請中包含的電話號碼是由預設的會議付費電話號碼和預設免付費電話號碼使用者的設定所定義。</span><span class="sxs-lookup"><span data-stu-id="831e5-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="831e5-110">每個設定會指定指定使用者的會議邀請中會包含哪些付費和免付費號碼。</span><span class="sxs-lookup"><span data-stu-id="831e5-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="831e5-111">如上所述，每個會議邀請都包含一個付費號碼、一個選擇性免付費號碼，以及一個連結，可開啟可用來加入給定會議之所有撥入電話號碼的完整清單。</span><span class="sxs-lookup"><span data-stu-id="831e5-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="831e5-112">對於新使用者，預設會議付費號碼會根據使用者啟用音訊會議服務的 Microsoft 365 系統管理中心所設定之使用位置來指派。</span><span class="sxs-lookup"><span data-stu-id="831e5-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="831e5-113">如果會議橋接器中的付費號碼符合使用者的國家/地區，該號碼會自動指派為使用者的預設付費號碼。</span><span class="sxs-lookup"><span data-stu-id="831e5-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="831e5-114">如果沒有號碼，則定義為會議橋接器預設付費號碼的號碼會指派為使用者的預設付費號碼。</span><span class="sxs-lookup"><span data-stu-id="831e5-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="831e5-115">使用者啟用音訊會議服務後，租使用者系統管理員隨時都可以從使用者的初始值變更使用者的預設付費和免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="831e5-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="831e5-116">設定或變更會議召集人或使用者的預設音訊會議電話號碼</span><span class="sxs-lookup"><span data-stu-id="831e5-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="831e5-117">![顯示 Microsoft Teams 標誌的圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="831e5-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="831e5-118">您必須是 Teams 服務系統管理員才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="831e5-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="831e5-119">請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。</span><span class="sxs-lookup"><span data-stu-id="831e5-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="831e5-120">登入 Microsoft Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="831e5-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="831e5-121">在左側流覽中，按一下 [ **使用者>**。</span><span class="sxs-lookup"><span data-stu-id="831e5-121">In the left navigation, click **Users**.</span></span>

    ![顯示在 Microsoft Teams 系統管理中心選取使用者](media/Admin-users.png)

3. <span data-ttu-id="831e5-123">從可用使用者清單中按一下使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="831e5-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="831e5-124">在 [ **音訊會議」 旁**，按一下 [ **編輯>**。</span><span class="sxs-lookup"><span data-stu-id="831e5-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![按一下音訊會議旁的 [編輯](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="831e5-126">使用 **付費號碼** 或 **免付費號碼欄位** 輸入使用者的數位。</span><span class="sxs-lookup"><span data-stu-id="831e5-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="831e5-127">當您變更使用者的音訊會議設定時，週期性和未來 Microsoft Teams 會議必須更新併發送給出席者。</span><span class="sxs-lookup"><span data-stu-id="831e5-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="831e5-128">想要使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="831e5-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="831e5-129">Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="831e5-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="831e5-130">使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="831e5-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="831e5-131">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="831e5-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="831e5-132">為什麼您需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="831e5-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="831e5-133">[使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="831e5-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="831e5-134">有關 Windows PowerShell 的資訊，請參閱 [Microsoft Teams PowerShell 參考](/powershell/module/teams/?view=teams-ps) 以瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="831e5-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="831e5-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="831e5-135">Related topics</span></span>

[<span data-ttu-id="831e5-136">在 Microsoft 365 或 Office 365 中試用或購買音訊會議</span><span class="sxs-lookup"><span data-stu-id="831e5-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="831e5-137">變更音訊會議橋接器的電話號碼</span><span class="sxs-lookup"><span data-stu-id="831e5-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)