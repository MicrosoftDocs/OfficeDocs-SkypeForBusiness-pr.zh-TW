---
title: 使用 Microsoft Teams 和 Bookings 應用程式進行虛擬會面
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 使用 Bookings 應用程式進行 Microsoft Teams 和虛擬會面
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125746"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="91107-103">使用 Microsoft Teams 和 Bookings 應用程式進行虛擬會面</span><span class="sxs-lookup"><span data-stu-id="91107-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="91107-104">Microsoft Teams 中的 Bookings 應用程式提供一種簡單的方式，可預約面對面及虛擬會面，例如醫療保健看診、財務諮詢、面試、客戶支援、教育處室時間等等。</span><span class="sxs-lookup"><span data-stu-id="91107-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="91107-105">排程器可以從單一體驗管理多個部門與員工行事曆，以及與內部和外部出席者之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="91107-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="91107-106">虛擬會面本身透過 Microsoft Teams 會議進行，提供強大的會議功能。</span><span class="sxs-lookup"><span data-stu-id="91107-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="91107-107">只有排程器需要在 Teams 中安裝 Bookings 應用程式。</span><span class="sxs-lookup"><span data-stu-id="91107-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="91107-108">進行或參與虛擬會面的員工不需要應用程式。</span><span class="sxs-lookup"><span data-stu-id="91107-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="91107-109">他們只需透過 Outlook 或 Teams 行事曆，或是預約確認電子郵件中的連結即可加入會面。</span><span class="sxs-lookup"><span data-stu-id="91107-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="91107-110">在 Teams 中使用 Bookings 應用程式的必要條件</span><span class="sxs-lookup"><span data-stu-id="91107-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="91107-111">Exchange 信箱必須位在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="91107-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="91107-112">不支援內部部署 Exchange Server 信箱。</span><span class="sxs-lookup"><span data-stu-id="91107-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="91107-113">必須為組織開啟 Microsoft Bookings。</span><span class="sxs-lookup"><span data-stu-id="91107-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="91107-114">使用者必須擁有適當的授權。</span><span class="sxs-lookup"><span data-stu-id="91107-114">Users must have an appropriate license.</span></span> <span data-ttu-id="91107-115">支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準版、A3、A5、E3 和 E5。</span><span class="sxs-lookup"><span data-stu-id="91107-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="91107-116">Bookings 應用程式的所有使用者，以及所有參與會議的員工都必須擁有支援 Teams 會議排程授權。</span><span class="sxs-lookup"><span data-stu-id="91107-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="91107-117">您的系統必須符合所有[軟體與瀏覽器必要條件](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="91107-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="91107-118">Teams 中的 Bookings 可用性</span><span class="sxs-lookup"><span data-stu-id="91107-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="91107-119">適用於 Teams 的 Microsoft Bookings 應用程式可在桌面和 Web 上使用。</span><span class="sxs-lookup"><span data-stu-id="91107-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="91107-120">您可以在 [Microsoft Teams 中的 應用程式](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 下，以及 Teams 系統管理中心的 **管理應用程式** 下找到。</span><span class="sxs-lookup"><span data-stu-id="91107-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="91107-121">控制貴組織中 Bookings 的存取權</span><span class="sxs-lookup"><span data-stu-id="91107-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="91107-122">有幾種方法可控制能存取 Bookings 應用程式及應用程式特定功能的人員。</span><span class="sxs-lookup"><span data-stu-id="91107-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="91107-123">如需了解如何在 Microsoft 365 系統管理中心開啟或關閉 Microsoft Bookings，以及如何建立 Bookings 應用程式原則以讓選取的使用者建立 Bookings 行事曆，請參閱[取得 Microsoft Bookings](https://support.microsoft.com/zh-TW/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。</span><span class="sxs-lookup"><span data-stu-id="91107-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/zh-TW/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="91107-124">您也可以了解如何[建立 Teams 應用程式原則，以釘選特定使用者的 Bookings 應用程式](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="91107-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="91107-125">建議的會議原則設定</span><span class="sxs-lookup"><span data-stu-id="91107-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="91107-126">如需為 Bookings 啟用最佳體驗，請建立人員會議原則，以自動准許 **您組織的中所有人**。</span><span class="sxs-lookup"><span data-stu-id="91107-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="91107-127">這可讓員工自動加入會面，並啟用外部出席者的大廳體驗。</span><span class="sxs-lookup"><span data-stu-id="91107-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="91107-128">您可以深入了解如何[自動准許人員參加會議](meeting-policies-in-teams.md#automatically-admit-people)。</span><span class="sxs-lookup"><span data-stu-id="91107-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="91107-129">選擇性員工核准設定</span><span class="sxs-lookup"><span data-stu-id="91107-129">Optional staff approvals setting</span></span>

<span data-ttu-id="91107-130">作為額外的隱私權設定，您可以選擇員工得先加入後，才能透過 Bookings 分享其排程可用性資訊，以及預約會面。</span><span class="sxs-lookup"><span data-stu-id="91107-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="91107-131">如需啟用此設定，請前往 **Microsoft 365 系統管理中心** \> **設定** \> **設定**，然後選取 **Bookings**。</span><span class="sxs-lookup"><span data-stu-id="91107-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="91107-132">開啟此設定後，員工會收到一封電子郵件，要求他們核准預約行事曆的成員資格。</span><span class="sxs-lookup"><span data-stu-id="91107-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="91107-133">這項功能正逐步向全球 Microsoft 365 和 Office 365 客戶推出。</span><span class="sxs-lookup"><span data-stu-id="91107-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="91107-134">如果環境中尚未提供所有選項，請之後再返回查看。</span><span class="sxs-lookup"><span data-stu-id="91107-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="91107-135">在設定 Bookings 信箱時變更您的預設網域</span><span class="sxs-lookup"><span data-stu-id="91107-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="91107-136">設定 Bookings 信箱時，系統會使用 Microsoft 365 或 Office 365 組織的預設電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="91107-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="91107-137">不過，這可能會導致將會議邀請傳送給外部收件者時發生問題；您的邀請可能會被標為垃圾郵件，且移至收件者的垃圾郵件資料夾，因此收件者可能永遠不會看到您的邀請。</span><span class="sxs-lookup"><span data-stu-id="91107-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="91107-138">建議您在建立 Bookings 信箱之前先變更預設網域。</span><span class="sxs-lookup"><span data-stu-id="91107-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="91107-139">如需了解如何執行這項功能，請參閱[網域常見問題](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="91107-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="91107-140">如果您在 Bookings 信箱建立之後需要變更預設網域，您可以使用 PowerShell 執行此作業：</span><span class="sxs-lookup"><span data-stu-id="91107-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="91107-141">如需詳細資訊，請參閱 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 文件。</span><span class="sxs-lookup"><span data-stu-id="91107-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="91107-142">如果您使用 Exchange 混合式原則，建議您在變更預設網域時，徹底測試內部部署 Exchange 和 Exchange Online 之間的郵件流程。</span><span class="sxs-lookup"><span data-stu-id="91107-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="91107-143">傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="91107-143">Sending feedback</span></span>

<span data-ttu-id="91107-144">歡迎您提供寶貴的意見：</span><span class="sxs-lookup"><span data-stu-id="91107-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="91107-145">使用者體驗或便於使用</span><span class="sxs-lookup"><span data-stu-id="91107-145">User experience or ease of use</span></span>
  - <span data-ttu-id="91107-146">功能差距或功能遺失</span><span class="sxs-lookup"><span data-stu-id="91107-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="91107-147">Bug 或問題</span><span class="sxs-lookup"><span data-stu-id="91107-147">Bugs or issues</span></span>
  
<span data-ttu-id="91107-148">如需傳送意見，請按一下 Teams 左側瀏覽列底部附近的 **[說明]** 按鈕，然後針對 **[所有]** 問題按一下 **[回報問題]**。</span><span class="sxs-lookup"><span data-stu-id="91107-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="91107-149">請在您的意見反應報告開頭處標註，您傳送的是有關「Bookings」的意見，以便我們識別 Bookings 問題。</span><span class="sxs-lookup"><span data-stu-id="91107-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="91107-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="91107-150">Related topics</span></span>

<span data-ttu-id="91107-151">
  [適用於終端使用者的 Bookings 文件](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="91107-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>
