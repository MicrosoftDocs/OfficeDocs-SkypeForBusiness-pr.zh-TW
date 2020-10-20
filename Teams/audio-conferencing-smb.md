---
title: 針對中小型企業設定音訊會議
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
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
description: '瞭解如何在中小型企業中為需要使用電話撥入會議的人員設定音訊會議。 '
ms.openlocfilehash: b692654a0a874ea0c07f074daefe203aef2f80bc
ms.sourcegitcommit: 764605e226bc7d9cf45e9833c758d30da29132c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594644"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a><span data-ttu-id="4347a-103">針對中小型企業設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="4347a-103">Set up Audio Conferencing for small and medium businesses</span></span>

<span data-ttu-id="4347a-104">透過音訊會議，使用者可以使用電話撥入團隊會議，而不是在行動裝置或電腦上使用 [小組] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4347a-104">With Audio Conferencing, people can call in to Teams meetings using a phone instead of using the Teams app on their mobile device or from their computer.</span></span>  

<span data-ttu-id="4347a-105">如果您是最多300個使用者的中小型企業或中型企業，而且您目前沒有任何音訊會議授權，您可以在一年免費取得語音會議。</span><span class="sxs-lookup"><span data-stu-id="4347a-105">If you're a small or medium-sized business with up to 300 users and you currently don’t have any Audio Conferencing licenses, you can get Audio Conferencing free for one year.</span></span> <span data-ttu-id="4347a-106">此免費優惠于2020年10月1日起提供。</span><span class="sxs-lookup"><span data-stu-id="4347a-106">This free offer is available starting October 1, 2020.</span></span>

<span data-ttu-id="4347a-107">您可以將音訊會議附加元件授權套用至擁有 Microsoft 365 商務基本版、商務標準版、Business Premium、企業版 E1 或企業版 E3 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="4347a-107">The Audio Conferencing add-on license can be applied to users who have Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1, or Enterprise E3 licenses.</span></span> <span data-ttu-id="4347a-108">若要深入瞭解，請參閱 [小組附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="4347a-108">To learn more, see [Teams add-on licenses](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

> [!NOTE]
> <span data-ttu-id="4347a-109">如果您有企業版 E5 或 Microsoft 365 商務語音，您將無法使用免費的音訊會議優惠，因為這些授權已包含音訊會議。</span><span class="sxs-lookup"><span data-stu-id="4347a-109">If you have Enterprise E5 or Microsoft 365 Business Voice, you won't be able to use the free Audio Conferencing offer because these licenses already include Audio Conferencing.</span></span>

<span data-ttu-id="4347a-110">在本文中，我們將逐步引導您瞭解如何設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="4347a-110">In this article, we'll walk you through how to set up Audio Conferencing.</span></span> <span data-ttu-id="4347a-111">您只需要為打算排程或主持會議的人員設定音訊會議即可。</span><span class="sxs-lookup"><span data-stu-id="4347a-111">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="4347a-112">呼叫會議的出席者不需要授權或其他設定。</span><span class="sxs-lookup"><span data-stu-id="4347a-112">Meeting attendees who call in to meetings don't need licenses or other setup.</span></span> <span data-ttu-id="4347a-113">若要深入瞭解，請參閱 [音訊會議](audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="4347a-113">To learn more, see [Audio Conferencing](audio-conferencing-in-office-365.md).</span></span>

## <a name="set-up-audio-conferencing"></a><span data-ttu-id="4347a-114">設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="4347a-114">Set up Audio Conferencing</span></span>

<span data-ttu-id="4347a-115">當您設定音訊會議時，系統會自動將電話號碼指派給您的會議橋接器，以便在會議邀請中使用。</span><span class="sxs-lookup"><span data-stu-id="4347a-115">When you set up Audio Conferencing, a phone number is automatically assigned to your conferencing bridge so that it can be used in meeting invitations.</span></span> <span data-ttu-id="4347a-116">指派為會議橋接器預設號碼的電話號碼將是貴組織的國家或地區。</span><span class="sxs-lookup"><span data-stu-id="4347a-116">The phone number that's assigned as the default number of your conferencing bridge will be one from the country or region of your organization.</span></span> <span data-ttu-id="4347a-117">此電話號碼是收費的電話號碼，可能需要支付長途費用。</span><span class="sxs-lookup"><span data-stu-id="4347a-117">This phone number is a toll number, in which long-distance charges may apply.</span></span>

> [!NOTE]
> <span data-ttu-id="4347a-118">您也可以使用免付費電話號碼，這需要幾個額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="4347a-118">You can also use a toll-free number, which requires a few additional steps.</span></span> <span data-ttu-id="4347a-119">若要深入瞭解您的會議橋接器的電話號碼，請參閱本文稍後的 [音訊會議電話號碼](#audio-conferencing-phone-numbers) 。</span><span class="sxs-lookup"><span data-stu-id="4347a-119">To learn more about phone numbers for your conferencing bridge, see [Audio Conferencing phone numbers](#audio-conferencing-phone-numbers) later in this article.</span></span>

### <a name="step-1-get-audio-conferencing-licenses"></a><span data-ttu-id="4347a-120">步驟1：取得音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="4347a-120">Step 1: Get Audio Conferencing licenses</span></span>

<span data-ttu-id="4347a-121">針對將領導會議的每位人員，取得一個音訊會議授權。</span><span class="sxs-lookup"><span data-stu-id="4347a-121">Get one Audio Conferencing license for each person who will lead meetings.</span></span> <span data-ttu-id="4347a-122">使用 Microsoft 365 系統管理中心來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4347a-122">Use the Microsoft 365 admin center to do this.</span></span>

1. <span data-ttu-id="4347a-123">在 Microsoft 365 系統管理中心中，移至 [**帳單**  >  **購買服務**]，然後按一下頁面底部的 [**附加**元件]。</span><span class="sxs-lookup"><span data-stu-id="4347a-123">In the Microsoft 365 admin center, go to **Billing** > **Purchase services**, and then at the bottom of the page, select **Add-ons**.</span></span>
2. <span data-ttu-id="4347a-124">選取 [ **Microsoft 365 音訊會議採納促銷**  >  **詳細資料**]，然後選取 [**立即取得**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-124">Select **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, and then select **Get now**.</span></span>
3. <span data-ttu-id="4347a-125">輸入會議召集人所需的授權數量，然後完成您的訂單。</span><span class="sxs-lookup"><span data-stu-id="4347a-125">Enter the number of licenses you need for your meeting organizers, and then complete your order.</span></span>

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="音訊會議採用促銷授權的螢幕擷取畫面":::

    > [!NOTE]
    > <span data-ttu-id="4347a-127">根據您是否要將音訊會議授權自動指派給沒有此授權的所有使用者，清除或選取 [ **自動指派給沒有授權的所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-127">Clear or select the **Automatically assign to all of your users with no licenses**, depending on whether you want to automatically assign an Audio Conferencing license to all users who don't have this license.</span></span>

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a><span data-ttu-id="4347a-128">步驟2：指派音訊會議授權給領導會議的使用者</span><span class="sxs-lookup"><span data-stu-id="4347a-128">Step 2: Assign an Audio Conferencing license to users who lead meetings</span></span>

<span data-ttu-id="4347a-129">指派授權給將領導會議的每一個人。</span><span class="sxs-lookup"><span data-stu-id="4347a-129">Assign a license to each person who will lead meetings.</span></span> <span data-ttu-id="4347a-130">使用 Microsoft 365 系統管理中心來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4347a-130">Use the Microsoft 365 admin center to do this.</span></span>

#### <a name="assign-a-license-to-one-user"></a><span data-ttu-id="4347a-131">指派授權給一個使用者</span><span class="sxs-lookup"><span data-stu-id="4347a-131">Assign a license to one user</span></span>

1. <span data-ttu-id="4347a-132">在 Microsoft 365 系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-132">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="4347a-133">選取您要指派授權的使用者列，然後在窗格中選取 [ **授權及應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-133">Select the row of the user you want to assign the license to, and then in the pane, select **Licenses and Apps**.</span></span>
3. <span data-ttu-id="4347a-134">選取 [ **Microsoft 365 音訊會議** ] 核取方塊，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-134">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>

#### <a name="assign-a-license-to-multiple-users"></a><span data-ttu-id="4347a-135">指派授權給多位使用者</span><span class="sxs-lookup"><span data-stu-id="4347a-135">Assign a license to multiple users</span></span>

1. <span data-ttu-id="4347a-136">在 Microsoft 365 系統管理中心中，移至 [**使用者**作用中的  >  **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-136">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>  
2. <span data-ttu-id="4347a-137">選取您要指派授權的使用者旁邊的圓圈，然後選取 [ **管理產品授權**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-137">Select the circles next to the users you want to assign the license to, and then select **Manage product licenses**.</span></span>
3. <span data-ttu-id="4347a-138">在 [ **管理產品授權** ] 窗格中，選取 [ **指派更多**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-138">In the **Manage product licenses** pane, select **Assign more**.</span></span>
4. <span data-ttu-id="4347a-139">選取 [ **Microsoft 365 音訊會議** ] 核取方塊，然後選取 [ **儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-139">Select the **Microsoft 365 Audio Conferencing** check box, and then select **Save changes**.</span></span>  

## <a name="schedule-teams-meetings-in-outlook"></a><span data-ttu-id="4347a-140">在 Outlook 中排程團隊會議</span><span class="sxs-lookup"><span data-stu-id="4347a-140">Schedule Teams meetings in Outlook</span></span>

<span data-ttu-id="4347a-141">您的會議召集人現在可以在 Outlook 中排程會議。</span><span class="sxs-lookup"><span data-stu-id="4347a-141">Your meeting organizers can now schedule meetings in Outlook.</span></span> <span data-ttu-id="4347a-142">在 Outlook 中，移至 [行事 **曆**]，然後選取 [ **新增團隊會議** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4347a-142">In Outlook, go to **Calendar**, and then select the **New Teams meeting** button.</span></span> <span data-ttu-id="4347a-143">會議撥入號碼和會議 ID 會自動新增至傳送給會議出席者的會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="4347a-143">The meeting dial-in numbers and the conference ID are automatically added to the meeting invitation that's sent to meeting attendees.</span></span> <span data-ttu-id="4347a-144">若要深入瞭解，請參閱 [在 Outlook 中排程團隊會議](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)。</span><span class="sxs-lookup"><span data-stu-id="4347a-144">To learn more, see [Schedule a Teams meeting in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).</span></span>

> [!NOTE]
> <span data-ttu-id="4347a-145">如有需要，您可以自訂會議邀請來新增公司標誌、支援網站的連結和法律免責聲明，以及純文字的頁尾。</span><span class="sxs-lookup"><span data-stu-id="4347a-145">If you want, you can customize meeting invitations to add your company logo, links to your support website and legal disclaimer, and a text-only footer.</span></span> <span data-ttu-id="4347a-146">若要深入瞭解，請參閱 [自訂會議邀請](meeting-settings-in-teams.md#customize-meeting-invitations)。</span><span class="sxs-lookup"><span data-stu-id="4347a-146">To learn more, see [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>

## <a name="audio-conferencing-phone-numbers"></a><span data-ttu-id="4347a-147">音訊會議電話號碼</span><span class="sxs-lookup"><span data-stu-id="4347a-147">Audio Conferencing phone numbers</span></span>

<span data-ttu-id="4347a-148">您可以在會議橋接器中使用兩種類型的數位。</span><span class="sxs-lookup"><span data-stu-id="4347a-148">There are two types of numbers that you can use for your conferencing bridge.</span></span> <span data-ttu-id="4347a-149">您可以在本文前面的[設定音訊會議](#set-up-audio-conferencing)區段中使用**共用號碼** (，) 或**專屬號碼**。</span><span class="sxs-lookup"><span data-stu-id="4347a-149">You can use either **shared numbers** (as in the [Set up Audio Conferencing](#set-up-audio-conferencing) section earlier in this article) or **dedicated numbers**.</span></span> <span data-ttu-id="4347a-150">以下是每個程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4347a-150">Here's more information about each.</span></span>

### <a name="shared-numbers"></a><span data-ttu-id="4347a-151">共用號碼</span><span class="sxs-lookup"><span data-stu-id="4347a-151">Shared numbers</span></span>

<span data-ttu-id="4347a-152">共用號碼是在所有組織間共用的數位。</span><span class="sxs-lookup"><span data-stu-id="4347a-152">A shared number is a number that's shared across all organizations.</span></span> <span data-ttu-id="4347a-153">共用號碼是付費電話號碼，當您設定音訊會議時，系統會自動指派它。</span><span class="sxs-lookup"><span data-stu-id="4347a-153">Shared numbers are toll numbers and are automatically assigned when you set up Audio Conferencing.</span></span>

<span data-ttu-id="4347a-154">若要查看指派給您會議橋接器的預設號碼，請在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議橋接**]，然後找出最接近您的位置號碼。</span><span class="sxs-lookup"><span data-stu-id="4347a-154">To see the default number that's assigned to your conferencing bridge, in the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**, and then find the number for the location that's nearest to you.</span></span>

### <a name="dedicated-numbers"></a><span data-ttu-id="4347a-155">專用號碼</span><span class="sxs-lookup"><span data-stu-id="4347a-155">Dedicated numbers</span></span>

<span data-ttu-id="4347a-156">[專用號碼] 是只有您的使用者可以使用的數位。</span><span class="sxs-lookup"><span data-stu-id="4347a-156">A dedicated number is a number that's available only to your users.</span></span> <span data-ttu-id="4347a-157">專用號碼可以是收費電話號碼或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="4347a-157">A dedicated number can be a toll number or a toll-free number.</span></span> <span data-ttu-id="4347a-158">若要使用專用號碼，您必須先取得該號碼、將它指派給您的會議橋接器，然後將該號碼指派給將領導會議的每一個人。</span><span class="sxs-lookup"><span data-stu-id="4347a-158">To use a dedicated number, you'll have to first get the number, assign it to your conferencing bridge, and then assign the number to each person who will lead meetings.</span></span>

<span data-ttu-id="4347a-159">有幾種方法可以取得專用號碼。</span><span class="sxs-lookup"><span data-stu-id="4347a-159">There are a couple ways to get a dedicated number.</span></span> <span data-ttu-id="4347a-160">您可以從 Microsoft 取得號碼，或將現有的號碼從目前的服務提供者)  (埠轉接至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4347a-160">You can get a number from Microsoft or transfer (port) an existing number from your current service provider to Microsoft.</span></span> <span data-ttu-id="4347a-161">若要深入瞭解如何執行此動作，請參閱 [取得服務電話號碼](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="4347a-161">To learn more about how to do this, see [Getting service numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="4347a-162">請記住，如果您使用免付費電話號碼，您必須先將通訊信用授權指派給將領導會議的每一個人。</span><span class="sxs-lookup"><span data-stu-id="4347a-162">Keep in mind that if you use a toll-free number, you have to first assign a Communications Credits license to each person who will lead meetings.</span></span> <span data-ttu-id="4347a-163">若要深入瞭解，請參閱 [為您的組織設定通訊點數](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="4347a-163">To learn more, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

<span data-ttu-id="4347a-164">您有號碼之後，請將它指派給您的會議橋接器。</span><span class="sxs-lookup"><span data-stu-id="4347a-164">After you have your number, assign it to your conference bridge.</span></span> <span data-ttu-id="4347a-165">使用 Microsoft 團隊系統管理中心來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4347a-165">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="4347a-166">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議橋**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-166">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="4347a-167">選取 [ **新增**]，然後選取 [ **付費電話號碼** ] 或 [ **免付費電話號碼**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-167">Select **Add**, and then select **Toll number** or **Toll-free number**.</span></span>
3. <span data-ttu-id="4347a-168">在 [ **新增電話號碼** ] 窗格中 **，選取該**號碼，然後選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="4347a-168">In the **Add phone number** pane, select the number, and then select **Apply**.</span></span>

<span data-ttu-id="4347a-169">然後，將該號碼指派給將領導會議的每一個人。</span><span class="sxs-lookup"><span data-stu-id="4347a-169">Then, assign the number to each person who will lead meetings.</span></span> <span data-ttu-id="4347a-170">使用 Microsoft 團隊系統管理中心來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="4347a-170">Use the Microsoft Teams admin center to do this.</span></span>

1. <span data-ttu-id="4347a-171">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **使用者**]，按一下使用者的顯示名稱，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="4347a-171">In the left navigation of the Microsoft Teams admin center, select **Users**, click the display name of the user, and select **Edit**.</span></span>
2. <span data-ttu-id="4347a-172">選取 **Edit**[    **音訊會議**] 旁的 [編輯]，然後在 [ **音訊會議**   ] 窗格中，選取 [ **付費電話號碼**]   或 [ **免付費電話**號碼] 清單中的數位   ，然後選取**Apply**[套用]。</span><span class="sxs-lookup"><span data-stu-id="4347a-172">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, select a number in the **Toll number** or **Toll-free** number lists, and then select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4347a-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="4347a-173">Related topics</span></span>

- [<span data-ttu-id="4347a-174">音訊會議</span><span class="sxs-lookup"><span data-stu-id="4347a-174">Audio Conferencing</span></span>](audio-conferencing-in-office-365.md)
- [<span data-ttu-id="4347a-175">為小組設定音訊會議</span><span class="sxs-lookup"><span data-stu-id="4347a-175">Set up Audio Conferencing for Teams</span></span>](set-up-audio-conferencing-in-teams.md)
- [<span data-ttu-id="4347a-176">音訊會議的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4347a-176">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
- [<span data-ttu-id="4347a-177">音訊會議的常見問題</span><span class="sxs-lookup"><span data-stu-id="4347a-177">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
- [<span data-ttu-id="4347a-178">取得服務號碼</span><span class="sxs-lookup"><span data-stu-id="4347a-178">Getting service numbers</span></span>](getting-service-phone-numbers.md)
- [<span data-ttu-id="4347a-179">團隊附加元件授權</span><span class="sxs-lookup"><span data-stu-id="4347a-179">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="4347a-180">指派授權給使用者</span><span class="sxs-lookup"><span data-stu-id="4347a-180">Assign licenses to users</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
