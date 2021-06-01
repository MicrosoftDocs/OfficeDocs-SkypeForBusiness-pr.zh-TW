---
title: 在線上管理組織的音訊會議商務用 Skype設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: '請參閱商務用 Skype線上步驟，將電話撥入式會議授權和會議 ID 指派給使用者，以及許多其他電話撥入式會議設定。 '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237240"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="54ebb-103">在線上管理組織的音訊會議商務用 Skype設定</span><span class="sxs-lookup"><span data-stu-id="54ebb-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="54ebb-104">如果您想要在 Teams 管理這些設定，請參閱在 Microsoft Teams 中管理組織的[音訊會議Microsoft Teams。](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)</span><span class="sxs-lookup"><span data-stu-id="54ebb-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="54ebb-105">您可以更輕鬆地在單一位置查看所有商務用 Skype會議設定。</span><span class="sxs-lookup"><span data-stu-id="54ebb-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="54ebb-106">指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="54ebb-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="54ebb-107">您無法使用系統管理中心 **指派商務用 Skype授權**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="54ebb-108">您必須使用系統管理Microsoft 365中心。</span><span class="sxs-lookup"><span data-stu-id="54ebb-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="54ebb-109">請參閱[指派商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="54ebb-110">**為使用者指派授權**</span><span class="sxs-lookup"><span data-stu-id="54ebb-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="54ebb-111">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-112">在系統管理中心的左側導覽中，前往使用者活動使用者，然後從可用使用者清單中選取  >  使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54ebb-113">如果您同時將授權指派給最多 20 個使用者，您可以使用選取視圖下拉式清單，然後選擇其中一個選項，或建立您自己的視圖。</span><span class="sxs-lookup"><span data-stu-id="54ebb-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="54ebb-114">然後按一下 [**編輯，\*\*\*\*下** 一步兩次，然後選取授權並 **按一下 [提交**> 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="54ebb-115">您也可以使用 Powershell，將授權指派給Windows使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="54ebb-116">有關指示和 PowerShell 腳本範例，請參閱指派[商務用 Skype授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="54ebb-117">在 [產品授權」 下的 [動作 **窗格**> 中，按一下 **[編輯>**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="54ebb-118">在 [ **產品授權>** 頁面上，開啟 **音訊會議** ，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="54ebb-119">有關授權的更多內容，請參閱商務用 Skype[附加元件授權。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="54ebb-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="54ebb-120">指派授權之後，Microsoft 一開始可能不會在清單中顯示為音訊會議提供者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="54ebb-121">如果發生這種情況，請登出系統管理中心，或按 CTRL+F5 重新啟用瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="54ebb-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="54ebb-122">啟用或停用發送給音訊會議使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="54ebb-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="54ebb-123">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="54ebb-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="54ebb-124">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-125">請前往系統管理中心>商務用 Skype流覽左側的 [音訊 **會議**> 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="54ebb-126">在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="54ebb-127">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="54ebb-127">Click **Save**.</span></span>

    <span data-ttu-id="54ebb-128">您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以 **電子郵件傳送會議資訊**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="54ebb-129">會議邀請中包含會議 ID 和預設音訊會議電話號碼，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="54ebb-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="54ebb-130">請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="54ebb-131">**使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="54ebb-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="54ebb-132">您也可以使用以下Windows PowerShell執行：</span><span class="sxs-lookup"><span data-stu-id="54ebb-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="54ebb-133">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54ebb-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="54ebb-134">變更寄件者在電子郵件訊息中的連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="54ebb-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="54ebb-135">您可以變更自動發送給使用者的電子郵件，包括實際的電子郵件地址和寄件者連絡人資訊的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="54ebb-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="54ebb-136">根據預設，電子郵件的寄件者為 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來變更電子郵件地址和顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="54ebb-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="54ebb-137">若要變更傳送電子郵件給使用者的電子郵件地址，您必須：</span><span class="sxs-lookup"><span data-stu-id="54ebb-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="54ebb-138">在 _SendEmailFromAddress 參數中輸入_ 電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="54ebb-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="54ebb-139">在  _SendEmailFromDisplayName 參數中輸入電子郵件顯示_ 名稱。</span><span class="sxs-lookup"><span data-stu-id="54ebb-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="54ebb-140">將 _SendEmailOverride 參數_ 設為 _True_。</span><span class="sxs-lookup"><span data-stu-id="54ebb-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="54ebb-141">您可以對寄給使用者的電子郵件進行變更，例如電子郵件的寄回位址或電子郵件的顯示名稱，方式如下：</span><span class="sxs-lookup"><span data-stu-id="54ebb-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="54ebb-142">如果您想要變更電子郵件地址資訊，您必須確定貴組織的輸入電子郵件政策允許來自自訂電子郵件地址的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54ebb-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="54ebb-143">您可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54ebb-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="54ebb-144">請參閱 [當使用者的音訊會議設定變更時自動發送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="54ebb-145">重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="54ebb-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="54ebb-146">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-147">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-148">在 商務用 Skype系統管理中心，在左側流覽中，前往 [音訊會議」，在 [會議識別碼 **商務用 Skype** 動作窗格的 [重設> 中，按一下 [**重設**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="54ebb-149">在 [ **重設會議 ID？ 視窗中** ，按一下 **[是**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="54ebb-150">如果已啟用傳送電子郵件給使用者，系統會自動建立會議 ID，並傳送一封具有新會議 ID 的電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="54ebb-151">預設會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="54ebb-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="54ebb-152">建立新會議 ID 之後，來電者無法使用舊的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="54ebb-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="54ebb-153">您應該通知使用者重新排期現有的會議邀請，以確保新會議 ID 已新加入邀請中。</span><span class="sxs-lookup"><span data-stu-id="54ebb-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="54ebb-154">使用者可以使用會議移商務用 Skype工具來更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="54ebb-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="54ebb-155">若要瞭解如何下載、安裝及執行 商務用 Skype 會議更新工具，請參閱：商務用 Skype 和[Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)的會議更新工具、商務用 Skype Online、會議移移工具[ (64](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 商務用 Skype Online、會議移移工具[ (32](https://www.microsoft.com/download/details.aspx?id=54079)位) 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="54ebb-156">請參閱[重設使用者的會議 ID。](reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="54ebb-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="54ebb-157">重設會議召集人的 PIN</span><span class="sxs-lookup"><span data-stu-id="54ebb-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="54ebb-158">使用者排程的每個會議都會獲得唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="54ebb-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="54ebb-159">雖然會自動建立會議 ID 並指派給使用者，但有時候使用者可能不想使用此 ID，而您想要將其設定為特定號碼，或是您的使用者不記得或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="54ebb-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="54ebb-160">您可以使用系統管理商務用 Skype和Windows PowerShell來查看、變更及重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="54ebb-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="54ebb-161">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-162">請前往系統管理中心>商務用 Skype流覽左側的 [音訊 **會議**> 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="54ebb-163">按一下 **[** 使用者，然後選取要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="54ebb-164">在 [動作窗格的 **PIN** 中，按一下 [ **重設**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="54ebb-165">當使用者啟用音訊會議或 PIN 重設時，會收到一封包含 PIN 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="54ebb-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="54ebb-166">但如果您已停用自動傳送電子郵件，將不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="54ebb-167">PIN 在重設後只會顯示一次。</span><span class="sxs-lookup"><span data-stu-id="54ebb-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="54ebb-168">在重設後顯示 PIN 之後，PIN 不會再顯示在使用者屬性上;而是會顯示 \*\*\*\* 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="54ebb-169">請參閱 [重設音訊會議 PIN](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="54ebb-170">傳送包含音訊會議資訊的電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="54ebb-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="54ebb-171">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-172">請前往系統管理中心>商務用 Skype流覽左側的 [音訊 **會議**> 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="54ebb-173">按一下 **[** 使用者，然後選取要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="54ebb-174">在 [動作」 窗格中，按一下 **[透過電子郵件傳送會議資訊。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54ebb-175">當您這麼做時，音訊會議 PIN 不會發送給使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="54ebb-176">請參閱 [傳送包含音訊會議資訊的電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="54ebb-177">設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="54ebb-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="54ebb-178">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-179">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-180">在左側流覽中，前往 **音訊會議**  >  **使用者**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="54ebb-181">選取您想要為音訊會議啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="54ebb-182">在動作窗格中，您可以設定付費 **號碼** ，如果允許，也可以設定 **免付費號碼**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="54ebb-183">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="54ebb-183">Click **Save**.</span></span>

<span data-ttu-id="54ebb-184">請參閱 [設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="54ebb-185">選擇音訊會議橋接器設定</span><span class="sxs-lookup"><span data-stu-id="54ebb-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="54ebb-186">**設定來電者加入會議時的會議體驗**</span><span class="sxs-lookup"><span data-stu-id="54ebb-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="54ebb-187">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-188">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-189">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="54ebb-190">在 **會議加入體驗** 下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="54ebb-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="54ebb-191">**啟用會議進入和離開通知的開啟** 這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="54ebb-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="54ebb-192">如果您清除此核取方塊，根據預設，已加入會議的使用者不會在有人進入或離開會議時收到通知。</span><span class="sxs-lookup"><span data-stu-id="54ebb-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="54ebb-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span><span class="sxs-lookup"><span data-stu-id="54ebb-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="54ebb-194">**要求來電者在加入會議前先錄製他們的名稱** 這是預設選取的。</span><span class="sxs-lookup"><span data-stu-id="54ebb-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="54ebb-195">如果您清除此核取方塊，不會要求來電者在加入會議之前先記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="54ebb-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="54ebb-196">進行變更之後，請按一下 [**儲存。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="54ebb-197">請參閱 [變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="54ebb-198">**設定會議的 PIN 長度**</span><span class="sxs-lookup"><span data-stu-id="54ebb-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="54ebb-199">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-200">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-201">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議** Microsoft  >  **橋接器設定**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="54ebb-202">在 **[安全性**」 下，在 PIN 長度清單中輸入PIN 的位數，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="54ebb-203">PIN 必須介於 4 到 12 位數之間。</span><span class="sxs-lookup"><span data-stu-id="54ebb-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="54ebb-204">預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="54ebb-204">The default is 5.</span></span>
    
<span data-ttu-id="54ebb-205">請參閱 [變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="54ebb-206">**啟用或停用電子郵件，禁止將電子郵件發送給音訊使用者**</span><span class="sxs-lookup"><span data-stu-id="54ebb-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="54ebb-207">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-208">請前往系統管理中心>商務用 Skype流覽左側的 [音訊 **會議**> 。</span><span class="sxs-lookup"><span data-stu-id="54ebb-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="54ebb-209">在 **Microsoft 橋接器設定頁面上** ，選取或清除如果使用者的音訊會議設定變更，自動 **傳送電子郵件給使用者**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="54ebb-210">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="54ebb-210">Click **Save**.</span></span>

    <span data-ttu-id="54ebb-211">您也可以使用音訊會議設定傳送電子郵件給使用者，方法是流覽使用者的音訊會議屬性，然後按一下以 **電子郵件傳送會議資訊**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="54ebb-212">如果您這麼做，將會送出只包含會議 ID 和會議電話號碼的電子郵件，但不包含 PIN。</span><span class="sxs-lookup"><span data-stu-id="54ebb-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="54ebb-213">請參閱 [傳送電子郵件給使用者及其音訊會議資訊](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="54ebb-214">在音訊會議橋接器上 (主要) 次要 (次要) 替代語言</span><span class="sxs-lookup"><span data-stu-id="54ebb-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="54ebb-215">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-216">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-217">在 商務用 Skype **系統** 管理中心，在左側流覽中，前往 **[音訊會議**，然後按一下 **Microsoft 橋接器**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="54ebb-218">從清單中選取電話號碼，按一下 [動作窗格設定語言>，然後在 [設定語言>頁面上，按一下 [使用主要語言清單來查看支援的語言的完整清單。 </span><span class="sxs-lookup"><span data-stu-id="54ebb-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="54ebb-219">您也可以設定當您選取 Microsoft 做為音訊會議提供者時支援的主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="54ebb-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="54ebb-220">在清單中選取的順序與向來電者呈現語言的順序相同。</span><span class="sxs-lookup"><span data-stu-id="54ebb-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="54ebb-221">請參閱 [設定音訊會議的自動語音語音處理語言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="54ebb-222">查看音訊會議電話撥入號碼</span><span class="sxs-lookup"><span data-stu-id="54ebb-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="54ebb-223">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-224">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="54ebb-225">在 商務用 Skype **系統管理中心**，在左側流覽中，前往 **音訊會議**  >  **Microsoft 橋接器**。</span><span class="sxs-lookup"><span data-stu-id="54ebb-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="54ebb-226">您可以在這裡：</span><span class="sxs-lookup"><span data-stu-id="54ebb-226">Here you can:</span></span>

   - <span data-ttu-id="54ebb-227">查看音訊會議Microsoft 365或Office 365設定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="54ebb-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="54ebb-228">查看音訊會議自動語音機會使用的位置，以及主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="54ebb-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="54ebb-229">選取啟用音訊會議時將給予使用者的預設電話號碼。</span><span class="sxs-lookup"><span data-stu-id="54ebb-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="54ebb-230">不過，如果音訊會議橋接器的預設電話號碼變更，現有使用者的預設電話號碼不會變更。</span><span class="sxs-lookup"><span data-stu-id="54ebb-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="54ebb-231">您可以前往音訊 **會議** 使用者，然後選取使用者的屬性，以變更使用者的預設號碼，從貴組織中可用的號碼清單中選擇新  >  號碼。</span><span class="sxs-lookup"><span data-stu-id="54ebb-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="54ebb-232">請參閱 [查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="54ebb-233">查看已啟用的使用者清單</span><span class="sxs-lookup"><span data-stu-id="54ebb-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="54ebb-234">使用公司或學校帳戶來登錄。</span><span class="sxs-lookup"><span data-stu-id="54ebb-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="54ebb-235">請前往系統管理中心 **>商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="54ebb-236">在 商務用 Skype **系統** 管理中心，在左側流覽中，前往音訊會議>**使用者。**</span><span class="sxs-lookup"><span data-stu-id="54ebb-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="54ebb-237">請參閱 [查看已啟用音訊會議的使用者清單](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="54ebb-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="54ebb-238">想要瞭解如何使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="54ebb-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="54ebb-239">您可以在組織層級使用多個設定來管理Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="54ebb-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="54ebb-240">這可輕鬆地將設定適用于所有使用者。</span><span class="sxs-lookup"><span data-stu-id="54ebb-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="54ebb-241">若要取得每個 Cmdlet 的更多協助，[請參閱商務用 Skype Cmdlet。](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="54ebb-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="54ebb-242">以下是組織層級設定：</span><span class="sxs-lookup"><span data-stu-id="54ebb-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="54ebb-243">**設定進入/離開通知** 預設值 _為_$true。</span><span class="sxs-lookup"><span data-stu-id="54ebb-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="54ebb-244">**設定名稱錄製** 預設值 _為_$true。</span><span class="sxs-lookup"><span data-stu-id="54ebb-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="54ebb-245">**設定 PIN 長度** 預設值為 5。</span><span class="sxs-lookup"><span data-stu-id="54ebb-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="54ebb-246">**只從電話設定電話撥入會議** 預設 _$false。_</span><span class="sxs-lookup"><span data-stu-id="54ebb-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="54ebb-247">**設定是否要傳送電子郵件給使用者** 預設值 _為_$true。</span><span class="sxs-lookup"><span data-stu-id="54ebb-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="54ebb-248">**設定是否要從其他帳戶傳送電子郵件** 預設值  _為_$false。</span><span class="sxs-lookup"><span data-stu-id="54ebb-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="54ebb-249">**在電子郵件上設定要寄給使用者的 From 位址** 預設值 _為_$null。</span><span class="sxs-lookup"><span data-stu-id="54ebb-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="54ebb-250">**設定電子郵件的** 顯示名稱預設值  _為_$null。</span><span class="sxs-lookup"><span data-stu-id="54ebb-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="54ebb-251">想要進一Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54ebb-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="54ebb-252">Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="54ebb-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="54ebb-253">您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。</span><span class="sxs-lookup"><span data-stu-id="54ebb-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="54ebb-254">若要開始使用Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="54ebb-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="54ebb-255">為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="54ebb-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="54ebb-256">[使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="54ebb-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="54ebb-257">Windows PowerShell使用系統管理中心時，系統在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="54ebb-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="54ebb-258">請從下列主題瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="54ebb-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="54ebb-259">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="54ebb-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="54ebb-260">使用 Windows PowerShell 管理 商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="54ebb-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="54ebb-261">使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作</span><span class="sxs-lookup"><span data-stu-id="54ebb-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="54ebb-262">Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 的遠端商務用 Skype會話。</span><span class="sxs-lookup"><span data-stu-id="54ebb-262">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="54ebb-263">此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell[模組商務用 Skype Online。](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="54ebb-263">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="54ebb-264">相關主題</span><span class="sxs-lookup"><span data-stu-id="54ebb-264">Related topics</span></span>

[<span data-ttu-id="54ebb-265">管理使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="54ebb-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)
