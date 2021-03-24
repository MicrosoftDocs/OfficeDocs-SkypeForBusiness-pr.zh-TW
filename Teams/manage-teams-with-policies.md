---
title: 使用策略管理 Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解 Teams 政策。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b54c64c637d44132ac0f978561267ef34f720e67
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101099"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="73c3c-103">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="73c3c-103">Manage Teams with policies</span></span>

<span data-ttu-id="73c3c-104">策略是管理 Teams 的重要部分。</span><span class="sxs-lookup"><span data-stu-id="73c3c-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="73c3c-105">使用本文流覽如何使用策略來為貴組織帶來好處。</span><span class="sxs-lookup"><span data-stu-id="73c3c-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="73c3c-106">您用於策略的</span><span class="sxs-lookup"><span data-stu-id="73c3c-106">What you use policies for</span></span>

<span data-ttu-id="73c3c-107">策略用於完成貴組織中跨不同領域的許多工作，例如訊息、會議和應用程式。</span><span class="sxs-lookup"><span data-stu-id="73c3c-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="73c3c-108">您可以執行一些操作，包括允許使用者在團隊頻道中排程會議、讓使用者編輯已送出的郵件，以及控制使用者是否可以將應用程式釘到 Teams 應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="73c3c-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="73c3c-109">如何指派策略</span><span class="sxs-lookup"><span data-stu-id="73c3c-109">How to assign policies</span></span>

<span data-ttu-id="73c3c-110">根據貴組織嘗試完成的工作，可以數種不同的方式指派策略。</span><span class="sxs-lookup"><span data-stu-id="73c3c-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="73c3c-111">您可以在 Teams 系統管理中心進行和查看作業。</span><span class="sxs-lookup"><span data-stu-id="73c3c-111">You can make and view assignments in the Teams admin center.</span></span>

![群群組原則作業的螢幕擷取畫面。](media/group-policy-assignment.png)

<span data-ttu-id="73c3c-113">請在這裡閱讀有關指派策略 [的更多資訊](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="73c3c-113">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="73c3c-114">如何管理原則</span><span class="sxs-lookup"><span data-stu-id="73c3c-114">How to manage policies</span></span>

<span data-ttu-id="73c3c-115">使用 Microsoft Teams 系統管理中心或 [PowerShell 管理原則](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="73c3c-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="73c3c-116">例如，應用程式設定策略可以允許使用者上傳自訂應用程式、代表使用者安裝應用程式，以及將應用程式釘到 Teams 應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="73c3c-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="73c3c-117">這些策略在 Teams 系統管理中心中已配置。</span><span class="sxs-lookup"><span data-stu-id="73c3c-117">These policies are configured in the Teams admin center.</span></span>

![應用程式設定策略的螢幕擷取畫面。](media/app-setup-policy.png)

<span data-ttu-id="73c3c-119">此外，會議策略可用來控制 Teams 會議中的音訊和視音訊設定，例如文字記錄、雲端錄製和 IP 音訊/視像。</span><span class="sxs-lookup"><span data-stu-id="73c3c-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![會議策略的螢幕擷取畫面。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="73c3c-121">適用於教育的 Teams</span><span class="sxs-lookup"><span data-stu-id="73c3c-121">Teams for Education</span></span>

<span data-ttu-id="73c3c-122">您也可以使用 Teams [教育用策略精靈](easy-policy-setup-edu.md) ，輕鬆設定和管理學習環境的政策。</span><span class="sxs-lookup"><span data-stu-id="73c3c-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams 教育用策略精靈的螢幕擷取畫面。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="73c3c-124">政策類型</span><span class="sxs-lookup"><span data-stu-id="73c3c-124">Types of policies</span></span>

<span data-ttu-id="73c3c-125">您可以使用 Microsoft Teams 管理下列政策。</span><span class="sxs-lookup"><span data-stu-id="73c3c-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="73c3c-126">策略類型</span><span class="sxs-lookup"><span data-stu-id="73c3c-126">Policy type</span></span> | <span data-ttu-id="73c3c-127">說明</span><span class="sxs-lookup"><span data-stu-id="73c3c-127">Description</span></span>
------------|------------
[<span data-ttu-id="73c3c-128">策略套件</span><span class="sxs-lookup"><span data-stu-id="73c3c-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="73c3c-129">Microsoft Teams 中的策略套件是一組預先定義的策略和設定，您可以指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="73c3c-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="73c3c-130">會議原則</span><span class="sxs-lookup"><span data-stu-id="73c3c-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="73c3c-131">會議策略是用來控制貴組織中使用者排程會議之會議參與者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="73c3c-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="73c3c-132">會議政策包含下列主題。</span><span class="sxs-lookup"><span data-stu-id="73c3c-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="73c3c-133">- 音訊和視音訊政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-133">- Audio and video policies</span></span><br> <span data-ttu-id="73c3c-134">- 內容和螢幕畫面共用政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="73c3c-135">- 參與者、來賓和存取政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="73c3c-136">- 一般政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-136">- General policies</span></span>
[<span data-ttu-id="73c3c-137">語音和通話政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="73c3c-138">語音和通話政策會透過團隊管理這些設定，例如緊急通話、呼叫路由和本機號碼。</span><span class="sxs-lookup"><span data-stu-id="73c3c-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="73c3c-139">應用程式政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="73c3c-140">應用程式策略是用來控制 Microsoft Teams 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="73c3c-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="73c3c-141">系統管理員可以允許或封鎖使用者可以安裝的應用程式、將應用程式釘釘到使用者的 Teams 應用程式欄，以及代表使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="73c3c-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="73c3c-142">訊息原則</span><span class="sxs-lookup"><span data-stu-id="73c3c-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="73c3c-143">訊息策略可控制聊天和頻道功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="73c3c-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="73c3c-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="73c3c-144">Related topics</span></span>

* [<span data-ttu-id="73c3c-145">在 Microsoft Teams 中管理意見回饋政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-145">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="73c3c-146">在 Microsoft Teams 中管理團隊政策</span><span class="sxs-lookup"><span data-stu-id="73c3c-146">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="73c3c-147">在活動記錄中查看策略指派</span><span class="sxs-lookup"><span data-stu-id="73c3c-147">View policy assignments in the Activity Log</span></span>](activity-log.md)
* [<span data-ttu-id="73c3c-148">在 Microsoft Teams 中設定即時活動</span><span class="sxs-lookup"><span data-stu-id="73c3c-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="73c3c-149">Teams 教育用政策與政策套件</span><span class="sxs-lookup"><span data-stu-id="73c3c-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)