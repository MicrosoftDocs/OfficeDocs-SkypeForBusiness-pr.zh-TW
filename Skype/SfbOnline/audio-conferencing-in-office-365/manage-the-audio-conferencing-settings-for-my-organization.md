---
title: 在商務用 Skype Online 中管理我組織的音訊會議設定
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '若要將電話撥入式會議授權及會議 ID 指派給使用者和許多其他電話撥入式會議設定，請參閱商務用 Skype Online 步驟。 '
ms.openlocfilehash: f5597ae2b857569b7890d81577e4fd4252da5106
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962701"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="51fab-103">在商務用 Skype Online 中管理我組織的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="51fab-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="51fab-104">如果您想要在小組中管理這些設定，請參閱[在 Microsoft 團隊中管理組織的音訊會議設定](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="51fab-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="51fab-105">在單一位置查看商務用 Skype 的所有音訊會議設定可能會更容易。</span><span class="sxs-lookup"><span data-stu-id="51fab-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="51fab-106">指派音訊會議授權</span><span class="sxs-lookup"><span data-stu-id="51fab-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="51fab-107">您無法使用**商務用 Skype 系統管理中心**指派授權。</span><span class="sxs-lookup"><span data-stu-id="51fab-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="51fab-108">您必須使用 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="51fab-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="51fab-109">請參閱[指派商務用 Skype 授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="51fab-110">**指派使用者的授權**</span><span class="sxs-lookup"><span data-stu-id="51fab-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="51fab-111">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-112">在系統管理中心的左側導覽中，移至 [**使用者** > 作用中的**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51fab-113">如果您要同時指派授權給20個以上的使用者，您可以使用 [**選取視圖**] 下拉式清單，然後選擇其中一個選項，或建立您自己的 [視圖]。</span><span class="sxs-lookup"><span data-stu-id="51fab-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="51fab-114">然後按一下\*\*\*\*[編輯 **]，接著**兩次，選取授權，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="51fab-115">您也可以使用 Windows Powershell，將授權指派給多個使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="51fab-116">如需指示與範例 PowerShell 腳本，請參閱[指派商務用 Skype 授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="51fab-117">在 [**產品授權**] 底下的 [動作] 窗格中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="51fab-118">在 [**產品授權**] 頁面上，開啟 [**音訊會議**]，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="51fab-119">如需授權的詳細資訊，請參閱[商務用 Skype 附加元件授權](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51fab-120">指派授權之後，Microsoft 可能不會在清單中以音訊會議提供者的形式開始。</span><span class="sxs-lookup"><span data-stu-id="51fab-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="51fab-121">如果發生這種情況，請登出系統管理中心，或按 CTRL + F5 重新整理瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="51fab-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="51fab-122">啟用或停用傳送給音訊會議使用者的電子郵件</span><span class="sxs-lookup"><span data-stu-id="51fab-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="51fab-123">![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="51fab-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="51fab-124">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-125">移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="51fab-126">在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。</span><span class="sxs-lookup"><span data-stu-id="51fab-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="51fab-127">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-127">Click **Save**.</span></span>

    <span data-ttu-id="51fab-128">您也可以移至使用者的音訊會議屬性，然後按一下 [透過**電子郵件傳送會議資訊**]，以語音會議設定傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="51fab-129">會議 ID 和預設的音訊會議電話號碼包含在會議邀請中，但不包含在 PIN 中。</span><span class="sxs-lookup"><span data-stu-id="51fab-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="51fab-130">請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="51fab-131">**使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="51fab-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="51fab-132">您也可以使用 Windows PowerShell 並執行：</span><span class="sxs-lookup"><span data-stu-id="51fab-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="51fab-133">您可以使用 [[設定] CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="51fab-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="51fab-134">變更傳送給使用者的電子郵件訊息中的寄件者連絡人資訊</span><span class="sxs-lookup"><span data-stu-id="51fab-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="51fab-135">您可以對自動傳送給使用者的電子郵件進行變更，包括實際的電子郵件地址和寄件者連絡人資訊的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="51fab-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="51fab-136">根據預設，電子郵件的寄件者是 Office 365，但是您可以使用 Windows PowerShell 和[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來變更電子郵件地址和顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="51fab-136">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="51fab-137">若要對傳送電子郵件給使用者的電子郵件地址進行變更，您必須：</span><span class="sxs-lookup"><span data-stu-id="51fab-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="51fab-138">在_SendEmailFromAddress_參數中輸入電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="51fab-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="51fab-139">在_SendEmailFromDisplayName_參數中輸入電子郵件的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="51fab-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="51fab-140">將_SendEmailOverride_參數設定為_True_。</span><span class="sxs-lookup"><span data-stu-id="51fab-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="51fab-141">您可以執行下列動作，對傳送給使用者的電子郵件進行變更，例如電子郵件的寄件者電子郵件地址或電子郵件的顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="51fab-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="51fab-142">如果您想要變更電子郵件地址資訊，您必須確認貴組織的輸入電子郵件原則允許來自自訂電子郵件地址的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="51fab-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="51fab-143">您可以使用[CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 來管理貴組織的其他設定，包括電子郵件。</span><span class="sxs-lookup"><span data-stu-id="51fab-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="51fab-144">請參閱[在使用者的音訊會議設定變更時自動傳送給使用者的電子郵件](emails-sent-to-users-when-their-settings-change.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="51fab-145">重設會議 ID</span><span class="sxs-lookup"><span data-stu-id="51fab-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="51fab-146">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-147">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-148">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議**]，並在 [**會議 ID**] 底下的 [動作] 窗格中，按一下 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="51fab-149">在 [**重設會議 ID？** ] 視窗中，按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="51fab-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="51fab-150">如果已啟用傳送電子郵件給您的使用者，系統會自動建立會議 ID，並以新的會議 ID 傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="51fab-151">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="51fab-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="51fab-152">在建立新的會議 ID 之後，不能讓呼叫者使用舊的會議 id。</span><span class="sxs-lookup"><span data-stu-id="51fab-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="51fab-153">您應該通知使用者重新安排現有的會議邀請，以確保新的會議 ID 已新增到邀請中。</span><span class="sxs-lookup"><span data-stu-id="51fab-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="51fab-154">使用者可以使用商務用 Skype 會議遷移工具來更新現有的會議。</span><span class="sxs-lookup"><span data-stu-id="51fab-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="51fab-155">若要瞭解如何下載、安裝及執行商務用 Skype 會議更新工具，請參閱：[適用于商務用 skype 和 Lync 的會議更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[商務用 Skype Online、會議遷移工具（64位）](https://go.microsoft.com/fwlink/?LinkID=626047)，以及[商務用 Skype online、會議遷移工具（32位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="51fab-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="51fab-156">請參閱[重設使用者的會議 ID](reset-a-conference-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="51fab-157">重設會議召集人的 PIN</span><span class="sxs-lookup"><span data-stu-id="51fab-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="51fab-158">使用者排程的每個會議都會指派唯一的會議 ID。</span><span class="sxs-lookup"><span data-stu-id="51fab-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="51fab-159">雖然系統會自動建立會議 ID 並將其指派給使用者，但有時候使用者不想要使用此識別碼，而且您想要將它設定為特定的數位，或者您的使用者無法記住或遺失其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="51fab-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="51fab-160">您可以使用商務用 Skype 系統管理中心和 Windows PowerShell 來查看、變更及重設其會議 ID。</span><span class="sxs-lookup"><span data-stu-id="51fab-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="51fab-161">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-162">移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="51fab-163">按一下 [**使用者**]，然後選取您要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="51fab-164">在 [動作] 窗格的 [**釘**選] 底下，按一下 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="51fab-165">當使用者啟用音訊會議或 PIN 重設時，會收到一封電子郵件及其 PIN。</span><span class="sxs-lookup"><span data-stu-id="51fab-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="51fab-166">但如果您已停用自動傳送電子郵件，就不會傳送 PIN 重設電子郵件，您必須手動將 PIN 傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="51fab-167">PIN 只會在重定後顯示一次。</span><span class="sxs-lookup"><span data-stu-id="51fab-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="51fab-168">在重設之後，PIN 就不會再顯示在使用者屬性上;相反，\* \* \* \* \* 將會顯示。</span><span class="sxs-lookup"><span data-stu-id="51fab-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="51fab-169">請參閱[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="51fab-170">使用音訊會議資訊傳送電子郵件給使用者</span><span class="sxs-lookup"><span data-stu-id="51fab-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="51fab-171">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-172">移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="51fab-173">按一下 [**使用者**]，然後選取您要重設 PIN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="51fab-174">在 [動作] 窗格中，按一下 [透過**電子郵件傳送會議資訊**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51fab-175">當您這麼做時，音訊會議 PIN 不會傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="51fab-176">請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="51fab-177">設定邀請中包含的電話號碼</span><span class="sxs-lookup"><span data-stu-id="51fab-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="51fab-178">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-179">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-180">在左側導覽中，移至 [**音訊會議** > **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="51fab-181">選取您想要啟用音訊會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="51fab-182">在 [動作] 窗格中，您可以設定**付費電話號碼**，並在允許的情況下撥打免費**電話號碼**。</span><span class="sxs-lookup"><span data-stu-id="51fab-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="51fab-183">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-183">Click **Save**.</span></span>

<span data-ttu-id="51fab-184">請參閱[設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="51fab-185">選擇 [音訊會議橋接] 設定</span><span class="sxs-lookup"><span data-stu-id="51fab-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="51fab-186">**設定呼叫者加入會議時的會議體驗**</span><span class="sxs-lookup"><span data-stu-id="51fab-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="51fab-187">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-188">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-189">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="51fab-190">在 [**會議加入體驗**] 底下，選取下列動作：</span><span class="sxs-lookup"><span data-stu-id="51fab-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="51fab-191">[**啟用會議專案] 和 [結束通知] 以開啟**預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="51fab-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="51fab-192">如果您清除此核取方塊，當有人進入或離開會議時，預設已加入會議的使用者就不會收到通知。</span><span class="sxs-lookup"><span data-stu-id="51fab-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="51fab-193">當使用者使用商務用 Skype 應用程式加入會議，且在會議的 [Skype 會議**選項**] 功能表中修改 [**使用者進入或離開**] 設定時，可以在會議上進行設定。</span><span class="sxs-lookup"><span data-stu-id="51fab-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="51fab-194">**要求呼叫者在加入會議前記錄他們的名稱**預設會選取此選項。</span><span class="sxs-lookup"><span data-stu-id="51fab-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="51fab-195">如果您清除此核取方塊，則不會要求呼叫者在加入會議前記錄他們的名稱。</span><span class="sxs-lookup"><span data-stu-id="51fab-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="51fab-196">進行變更之後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="51fab-197">請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="51fab-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="51fab-198">**設定會議的 PIN 長度**</span><span class="sxs-lookup"><span data-stu-id="51fab-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="51fab-199">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-200">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-201">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器設定**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="51fab-202">在 [**安全性**] 底下的 [ **pin 長度**] 清單中，輸入您想要的 pin 數位位數，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="51fab-203">PIN 必須在4到12位數之間。</span><span class="sxs-lookup"><span data-stu-id="51fab-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="51fab-204">預設值為5。</span><span class="sxs-lookup"><span data-stu-id="51fab-204">The default is 5.</span></span>
    
<span data-ttu-id="51fab-205">請參閱[變更音訊會議橋接器的設定](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="51fab-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="51fab-206">**啟用或停用傳送電子郵件給音訊使用者的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="51fab-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="51fab-207">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-208">移至 [系統管理中心] >**商務用 Skype** ，然後在左側導覽中，按一下 [**音訊會議**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="51fab-209">在 [ **Microsoft 橋接器設定**] 頁面上，選取或清除 [**自動傳送電子郵件給使用者] （如果他們的音訊會議設定已變更**）。</span><span class="sxs-lookup"><span data-stu-id="51fab-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="51fab-210">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-210">Click **Save**.</span></span>

    <span data-ttu-id="51fab-211">您也可以移至使用者的音訊會議屬性，然後按一下 [透過**電子郵件傳送會議資訊**]，透過音訊會議設定傳送電子郵件給使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="51fab-212">如果您這樣做，就會傳送一封電子郵件，其中只包含會議 ID 和會議電話號碼，但不會包含該 PIN。</span><span class="sxs-lookup"><span data-stu-id="51fab-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="51fab-213">請參閱[使用音訊會議資訊傳送電子郵件給使用者](send-an-email-to-a-user-with-their-dial-in-information.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="51fab-214">在音訊會議橋中查看及設定主要（預設）和次要（替代）語言</span><span class="sxs-lookup"><span data-stu-id="51fab-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="51fab-215">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-216">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-217">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議**]，然後按一下 [ **Microsoft 橋接器**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="51fab-218">從清單中選取電話號碼，按一下 [動作] 窗格中的 [**設定語言**]，然後在 [**設定語言**] 頁面上，按一下 [使用**主要語言**] 清單來查看支援之語言的完整清單。</span><span class="sxs-lookup"><span data-stu-id="51fab-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="51fab-219">您也可以設定當您選取 Microsoft 作為音訊會議提供者時所支援的主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="51fab-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="51fab-220">您在清單中選取的順序與向呼叫者呈現語言的順序相同。</span><span class="sxs-lookup"><span data-stu-id="51fab-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="51fab-221">請參閱[設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="51fab-222">請參閱音訊會議撥入號碼</span><span class="sxs-lookup"><span data-stu-id="51fab-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="51fab-223">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-224">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-224">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-225">在**商務用 Skype 系統管理中心**的左導覽中，移至 [**音訊會議** > **Microsoft 橋接器**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="51fab-226">您可以在這裡進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="51fab-226">Here you can:</span></span>

   - <span data-ttu-id="51fab-227">查看由 Office 365 設定用來進行音訊會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="51fab-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="51fab-228">查看音訊會議自動語音應答將使用的位置，以及主要和次要語言。</span><span class="sxs-lookup"><span data-stu-id="51fab-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="51fab-229">選取在使用者啟用音訊會議時，系統會提供給使用者的預設電話號碼。</span><span class="sxs-lookup"><span data-stu-id="51fab-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="51fab-230">不過，如果音訊會議橋接的預設電話號碼變更了，現有使用者的預設電話號碼就不會變更。</span><span class="sxs-lookup"><span data-stu-id="51fab-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="51fab-231">您可以移至**音訊會議** > **使用者**，然後選取使用者的屬性，以變更使用者的預設號碼，方法是從您組織中可用的號碼清單中選擇新號碼。</span><span class="sxs-lookup"><span data-stu-id="51fab-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="51fab-232">請參閱[音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="51fab-233">查看已啟用的使用者清單</span><span class="sxs-lookup"><span data-stu-id="51fab-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="51fab-234">使用您的公司或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="51fab-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="51fab-235">移至 [系統管理中心] > [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="51fab-236">在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議**]>，然後移至 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="51fab-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="51fab-237">請參閱[查看已啟用音訊會議的使用者清單](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="51fab-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="51fab-238">想知道如何使用 Windows PowerShell 進行管理嗎？</span><span class="sxs-lookup"><span data-stu-id="51fab-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="51fab-239">您可以使用 Windows PowerShell 在組織層級管理幾個設定。</span><span class="sxs-lookup"><span data-stu-id="51fab-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="51fab-240">這可讓您輕鬆地將設定套用到所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="51fab-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="51fab-241">若要取得每個 Cmdlet 的詳細說明，請參閱[商務用 Skype Online Cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。</span><span class="sxs-lookup"><span data-stu-id="51fab-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="51fab-242">以下是組織層級設定：</span><span class="sxs-lookup"><span data-stu-id="51fab-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="51fab-243">**設定進入/結束通知**預設值為 [ _$true_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="51fab-244">**設定名稱錄製**預設值為 [ _$true_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="51fab-245">**設定 PIN 長度**預設值為5。</span><span class="sxs-lookup"><span data-stu-id="51fab-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="51fab-246">**僅從手機設定撥入會議**預設 _$false_。</span><span class="sxs-lookup"><span data-stu-id="51fab-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="51fab-247">**設定是否要將電子郵件傳送給使用者**預設值為 [ _$true_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="51fab-248">**設定是否要從不同的帳戶傳送電子郵件**預設值為 [ _$false_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="51fab-249">**在傳送給使用者的電子郵件上設定 [寄件者位址**]預設值為 [ _$null_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="51fab-250">**設定傳送給使用者的電子郵件顯示名稱**預設值為 [ _$null_]。</span><span class="sxs-lookup"><span data-stu-id="51fab-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="51fab-251">想要深入瞭解 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51fab-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="51fab-252">Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。</span><span class="sxs-lookup"><span data-stu-id="51fab-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="51fab-253">在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。</span><span class="sxs-lookup"><span data-stu-id="51fab-253">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="51fab-254">若要開始使用 Windows PowerShell，請參閱以下主題：</span><span class="sxs-lookup"><span data-stu-id="51fab-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="51fab-255">為什麼需要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="51fab-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="51fab-256">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="51fab-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="51fab-257">Windows PowerShell 的速度、簡潔性及生產率都有許多優點，只是使用系統管理中心，例如當您在一次為多位使用者進行設定變更時。</span><span class="sxs-lookup"><span data-stu-id="51fab-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="51fab-258">請參閱下列主題，瞭解這些優點：</span><span class="sxs-lookup"><span data-stu-id="51fab-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="51fab-259">Windows PowerShell 與 Lync Online 的簡介</span><span class="sxs-lookup"><span data-stu-id="51fab-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="51fab-260">使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="51fab-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="51fab-261">使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作</span><span class="sxs-lookup"><span data-stu-id="51fab-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="51fab-262">商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連接到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="51fab-262">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="51fab-263">此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="51fab-263">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="51fab-264">相關主題</span><span class="sxs-lookup"><span data-stu-id="51fab-264">Related topics</span></span>

[<span data-ttu-id="51fab-265">管理使用者的音訊會議設定</span><span class="sxs-lookup"><span data-stu-id="51fab-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


