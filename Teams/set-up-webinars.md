---
title: 在 Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何管理網路研討會Teams會議。
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718044"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="e897e-103">在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e897e-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="e897e-104">本文將協助您將組織設定為主持網路研討會。</span><span class="sxs-lookup"><span data-stu-id="e897e-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="e897e-105">什麼是網路研討會？</span><span class="sxs-lookup"><span data-stu-id="e897e-105">What are webinars?</span></span>

<span data-ttu-id="e897e-106">網路研討會是一種結構化會議，授課者與參與者都有明確角色，通常用於訓練目的或銷售與行銷潛在客戶產生案例。</span><span class="sxs-lookup"><span data-stu-id="e897e-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="e897e-107">在貴組織中設定網路研討會之後，您的使用者可以排程網路研討會，並開啟註冊給出席者。</span><span class="sxs-lookup"><span data-stu-id="e897e-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="e897e-108">與包含許多討論和工作分派的傳統會議不同，網路研討會適用于互動式簡報，並提供用於出席者分析的工具。</span><span class="sxs-lookup"><span data-stu-id="e897e-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="e897e-109">允許使用者使用 PowerShell 排程網路研討會</span><span class="sxs-lookup"><span data-stu-id="e897e-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="e897e-110">您可以在 **Set-CsTeamsMeetingPolicy** Cmdlet Windows PowerShell 中使用以下屬性來設定 Teams。</span><span class="sxs-lookup"><span data-stu-id="e897e-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="e897e-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="e897e-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="e897e-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="e897e-112">WhoCanRegister</span></span>
- <span data-ttu-id="e897e-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="e897e-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="e897e-114">請參閱 [Set-CsTeamsMeetingPolicy，](/powershell/module/skype/set-csteamsmeetingpolicy) 以在 Cmdlet 上獲得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e897e-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="e897e-115">執行這些 Cmdlet 之前，您必須連線至 商務用 Skype PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e897e-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="e897e-116">詳細資訊，請參閱使用[powerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)或 商務用 Skype 管理 Microsoft 365 Office 365 Online 。</span><span class="sxs-lookup"><span data-stu-id="e897e-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="e897e-117">允許使用者排程網路研討會</span><span class="sxs-lookup"><span data-stu-id="e897e-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="e897e-118">若要允許貴組織的使用者排程網路研討會，請執行：</span><span class="sxs-lookup"><span data-stu-id="e897e-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="e897e-119">設定誰可以註冊網路研討會</span><span class="sxs-lookup"><span data-stu-id="e897e-119">Configure who can register for webinars</span></span>

<span data-ttu-id="e897e-120">您可以只將註冊限制為貴組織的使用者，或將註冊開放給租使用者內外的每個人。</span><span class="sxs-lookup"><span data-stu-id="e897e-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="e897e-121">根據預設 **，WhoCanRegister** 會啟用並設定為 **所有人**。</span><span class="sxs-lookup"><span data-stu-id="e897e-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="e897e-122">如果您想要關閉會議註冊，請設定 **AllowMeetingRegistration** 為 **False**。</span><span class="sxs-lookup"><span data-stu-id="e897e-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e897e-123">請記住 **，AllowPrivateMeetingScheduling** 必須設為 **True，AllowMeetingRegistration** 可以工作。 </span><span class="sxs-lookup"><span data-stu-id="e897e-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="e897e-124">此外，Microsoft 清單必須設定在 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e897e-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="e897e-125">若要深入瞭解，請參閱 Microsoft [清單的控制項設定](/sharepoint/control-lists)。</span><span class="sxs-lookup"><span data-stu-id="e897e-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="e897e-126">**若要只允許 *貴* 組織的使用者註冊網路研討會，請執行：**</span><span class="sxs-lookup"><span data-stu-id="e897e-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="e897e-127">接著，執行：</span><span class="sxs-lookup"><span data-stu-id="e897e-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="e897e-128">**若要允許任何人 ，包括匿名使用者，註冊網路研討會，請執行：**</span><span class="sxs-lookup"><span data-stu-id="e897e-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="e897e-129">接著，執行：</span><span class="sxs-lookup"><span data-stu-id="e897e-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="e897e-130">如果在會議設定中關閉匿名加入，匿名使用者無法加入網路研討會。</span><span class="sxs-lookup"><span data-stu-id="e897e-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="e897e-131">若要深入瞭解並啟用此設定[，請參閱會議](meeting-settings-in-teams.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="e897e-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="e897e-132">收集會議出席人數</span><span class="sxs-lookup"><span data-stu-id="e897e-132">Collect meeting attendance</span></span>

<span data-ttu-id="e897e-133">如果您希望召集人分析誰註冊並參加網路研討會，您必須開啟 **AllowEngagementReport** 政策。</span><span class="sxs-lookup"><span data-stu-id="e897e-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="e897e-134">若要這麼做，請執行 PowerShell 中的下列命令。</span><span class="sxs-lookup"><span data-stu-id="e897e-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="e897e-135">設定網路研討會設定</span><span class="sxs-lookup"><span data-stu-id="e897e-135">Configure webinar settings</span></span>

<span data-ttu-id="e897e-136">啟用網路研討會環境之後，就不需要進一步系統管理員管理。</span><span class="sxs-lookup"><span data-stu-id="e897e-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="e897e-137">該政策會控制網路研討會召集人顯示的選項。</span><span class="sxs-lookup"><span data-stu-id="e897e-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e897e-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="e897e-138">Related topics</span></span>

- [<span data-ttu-id="e897e-139">會議Teams - 一般</span><span class="sxs-lookup"><span data-stu-id="e897e-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="e897e-140">Set-CsTeamsMeetingPolicy 檔</span><span class="sxs-lookup"><span data-stu-id="e897e-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
