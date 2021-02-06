---
title: 使用 Microsoft 團隊和預定 app 進行虛擬走訪
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
description: 使用預訂 App 進行 Microsoft 團隊和虛擬走訪
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125746"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="4fd73-103">使用 Microsoft 團隊和預定 app 進行虛擬走訪</span><span class="sxs-lookup"><span data-stu-id="4fd73-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="4fd73-104">Microsoft 團隊中的 [預定] 應用程式提供一種簡單的方式來排程人員與虛擬約會，例如醫療保健走訪、財務諮詢、訪談、客戶支援、教育 office 時間等。</span><span class="sxs-lookup"><span data-stu-id="4fd73-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="4fd73-105">計畫者可以管理多個部門和員工行事曆，以及從單一體驗中與內部及外部出席者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4fd73-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="4fd73-106">虛擬約會本身會透過 Microsoft 團隊會議進行舉行，提供強健的視訊會議功能。</span><span class="sxs-lookup"><span data-stu-id="4fd73-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd73-107">只有計畫者需要在小組中安裝預定 app。</span><span class="sxs-lookup"><span data-stu-id="4fd73-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="4fd73-108">員工進行或參與虛擬約會不需要 app。</span><span class="sxs-lookup"><span data-stu-id="4fd73-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="4fd73-109">他們可以直接從他們的 Outlook 或團隊行事曆，或從其預訂確認電子郵件中的連結加入約會。</span><span class="sxs-lookup"><span data-stu-id="4fd73-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="4fd73-110">在團隊中使用預定 app 的先決條件</span><span class="sxs-lookup"><span data-stu-id="4fd73-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="4fd73-111">Exchange 信箱必須位於 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="4fd73-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="4fd73-112">不支援內部部署 Exchange Server 信箱。</span><span class="sxs-lookup"><span data-stu-id="4fd73-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="4fd73-113">您必須為組織開啟 Microsoft 預訂。</span><span class="sxs-lookup"><span data-stu-id="4fd73-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="4fd73-114">使用者必須具備適當的授權。</span><span class="sxs-lookup"><span data-stu-id="4fd73-114">Users must have an appropriate license.</span></span> <span data-ttu-id="4fd73-115">支援 Office 365 A3、A5、E3 和 E5，以及 Microsoft 365 商務標準、A3、A5、E3 和 E5。</span><span class="sxs-lookup"><span data-stu-id="4fd73-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="4fd73-116">預訂 app 的所有使用者以及參與會議的所有人員都必須擁有支援小組會議排程的授權。</span><span class="sxs-lookup"><span data-stu-id="4fd73-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="4fd73-117">您的系統必須符合所有 [軟體和瀏覽器的先決條件](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd73-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="4fd73-118">團隊中的預訂可用性</span><span class="sxs-lookup"><span data-stu-id="4fd73-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="4fd73-119">您可以在桌面和 web 上取得適用于團隊的 Microsoft 預訂 App。</span><span class="sxs-lookup"><span data-stu-id="4fd73-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="4fd73-120">它可以在 [Microsoft 團隊內](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 的 [應用程式] 底下，在 [管理團隊內的 **App** ] 系統管理中心找到。</span><span class="sxs-lookup"><span data-stu-id="4fd73-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="4fd73-121">控制貴組織內的預訂存取權</span><span class="sxs-lookup"><span data-stu-id="4fd73-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="4fd73-122">有幾種方式可以控制誰有權存取預訂 app，以及應用程式的特定功能。</span><span class="sxs-lookup"><span data-stu-id="4fd73-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="4fd73-123">若要瞭解如何在 Microsoft 365 系統管理中心開啟或關閉 Microsoft 預訂，以及如何建立預訂 app 原則，以允許選取的使用者建立預定行事曆，請參閱 [取得 Microsoft 預訂的存取權](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)。</span><span class="sxs-lookup"><span data-stu-id="4fd73-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="4fd73-124">您也可以瞭解如何 [建立團隊 app 原則，以釘選使用者的預訂 app](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd73-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="4fd73-125">建議的會議原則設定</span><span class="sxs-lookup"><span data-stu-id="4fd73-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="4fd73-126">若要為預訂提供最佳的使用體驗，請建立員工會議原則來自動承認 **貴組織中的每個人**。</span><span class="sxs-lookup"><span data-stu-id="4fd73-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="4fd73-127">這可讓員工自動加入約會，並啟用外部出席者的會議廳體驗。</span><span class="sxs-lookup"><span data-stu-id="4fd73-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="4fd73-128">您可以深入瞭解如何 [將人員自動 admitting 到會議](meeting-policies-in-teams.md#automatically-admit-people)。</span><span class="sxs-lookup"><span data-stu-id="4fd73-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="4fd73-129">選用員工核准設定</span><span class="sxs-lookup"><span data-stu-id="4fd73-129">Optional staff approvals setting</span></span>

<span data-ttu-id="4fd73-130">如果您是額外的隱私權設定，您可以選擇 [要求員工在排程的可用性資訊透過預訂共用之後，且可在預訂約會前進行選擇。</span><span class="sxs-lookup"><span data-stu-id="4fd73-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="4fd73-131">若要啟用此設定，請移至 **Microsoft 365 系統管理中心** \> **設定** \> **設定**，然後選取 [ **預定**]。</span><span class="sxs-lookup"><span data-stu-id="4fd73-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="4fd73-132">開啟此設定時，員工將會收到一封電子郵件，要求他們在其中向預定行事曆核准成員資格。</span><span class="sxs-lookup"><span data-stu-id="4fd73-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="4fd73-133">這項功能在全球範圍內逐漸推出給 Microsoft 365 和 Office 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="4fd73-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="4fd73-134">如果您的環境中尚未提供所有選項，請稍後再查看。</span><span class="sxs-lookup"><span data-stu-id="4fd73-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="4fd73-135">在設定預訂信箱時變更您的預設網域</span><span class="sxs-lookup"><span data-stu-id="4fd73-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="4fd73-136">在設定預訂信箱時，會使用您的 Microsoft 365 或 Office 365 組織的預設電子郵件網域。</span><span class="sxs-lookup"><span data-stu-id="4fd73-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="4fd73-137">不過，這可能會在傳送會議邀請給外部收件者時發生問題;您的邀請可能會標示為垃圾郵件，並移至收件者的 [垃圾郵件] 資料夾，所以收件者可能不會看到您的邀請。</span><span class="sxs-lookup"><span data-stu-id="4fd73-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="4fd73-138">建議您先變更預設網域，然後再建立您的預定信箱。</span><span class="sxs-lookup"><span data-stu-id="4fd73-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="4fd73-139">如需如何執行此動作的詳細資訊，請參閱 [網域常見問題](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="4fd73-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="4fd73-140">如果您在已建立預定信箱後需要變更預設網域，您可以使用 PowerShell 進行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4fd73-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="4fd73-141">如需詳細資訊，請參閱 [設定信箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) Cmdlet 的 PowerShell 檔。</span><span class="sxs-lookup"><span data-stu-id="4fd73-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd73-142">如果您使用的是 Exchange 混合式設定，我們建議您在變更預設網域時，在內部部署 Exchange 和 Exchange Online 之間徹底測試郵件流程。</span><span class="sxs-lookup"><span data-stu-id="4fd73-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="4fd73-143">傳送意見反應</span><span class="sxs-lookup"><span data-stu-id="4fd73-143">Sending feedback</span></span>

<span data-ttu-id="4fd73-144">我們歡迎您提供意見反應：</span><span class="sxs-lookup"><span data-stu-id="4fd73-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="4fd73-145">使用者體驗或易用性</span><span class="sxs-lookup"><span data-stu-id="4fd73-145">User experience or ease of use</span></span>
  - <span data-ttu-id="4fd73-146">功能缺口或遺失的功能</span><span class="sxs-lookup"><span data-stu-id="4fd73-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="4fd73-147">錯誤或問題</span><span class="sxs-lookup"><span data-stu-id="4fd73-147">Bugs or issues</span></span>
  
<span data-ttu-id="4fd73-148">若要傳送意見反應，請 **按一下位於小組** 左側導覽列附近的 [說明] 按鈕，然後按一下 [針對 **所有** 問題 **報告問題**]。</span><span class="sxs-lookup"><span data-stu-id="4fd73-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="4fd73-149">請注意，您要傳送意見反應給您的意見反應報告開始，您會收到「預定」的意見反應，讓我們可以輕鬆找出預訂問題。</span><span class="sxs-lookup"><span data-stu-id="4fd73-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4fd73-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="4fd73-150">Related topics</span></span>

[<span data-ttu-id="4fd73-151">最終使用者的預定檔</span><span class="sxs-lookup"><span data-stu-id="4fd73-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
