---
title: 使用策略管理 Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421298"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="d6344-102">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="d6344-102">Manage Teams with policies</span></span>

<span data-ttu-id="d6344-103">策略是管理 Teams 的重要一部分。</span><span class="sxs-lookup"><span data-stu-id="d6344-103">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="d6344-104">使用本文流覽如何使用對貴組織有説明的政策。</span><span class="sxs-lookup"><span data-stu-id="d6344-104">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="d6344-105">您用於</span><span class="sxs-lookup"><span data-stu-id="d6344-105">What you use policies for</span></span>

<span data-ttu-id="d6344-106">策略是用來完成貴組織中跨不同領域的許多工作，例如傳訊、會議和應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6344-106">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="d6344-107">您可以執行一些操作，包括允許使用者在 Teams 頻道中排程會議、讓使用者編輯已送出的郵件，以及控制使用者是否可以將應用程式釘到 Teams 應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="d6344-107">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="d6344-108">如何指派策略</span><span class="sxs-lookup"><span data-stu-id="d6344-108">How to assign policies</span></span>

<span data-ttu-id="d6344-109">您可以根據貴組織嘗試完成的工作，以數種不同的方式指派策略。</span><span class="sxs-lookup"><span data-stu-id="d6344-109">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="d6344-110">您可以在 Teams 系統管理中心製作和查看作業。</span><span class="sxs-lookup"><span data-stu-id="d6344-110">You can make and view assignments in the Teams admin center.</span></span>

![群組原則指派的螢幕擷取畫面。](media/group-policy-assignment.png)

<span data-ttu-id="d6344-112">請在這裡閱讀有關指派策略 [的更多資訊](assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d6344-112">Read more about assigning policies [here](assign-policies.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="d6344-113">如何管理政策</span><span class="sxs-lookup"><span data-stu-id="d6344-113">How to manage policies</span></span>

<span data-ttu-id="d6344-114">使用 Microsoft Teams 系統管理中心或 [PowerShell 管理原則](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d6344-114">Policies are managed with the Microsoft Teams admin center or [using PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell).</span></span>

<span data-ttu-id="d6344-115">例如，應用程式設定政策允許您允許使用者上傳自訂應用程式、代表使用者安裝應用程式，以及將應用程式釘到 Teams 應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="d6344-115">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="d6344-116">這些策略在 Teams 系統管理中心中已進行配置。</span><span class="sxs-lookup"><span data-stu-id="d6344-116">These policies are configured in the Teams admin center.</span></span>

![應用程式設定策略的螢幕擷取畫面。](media/app-setup-policy.png)

<span data-ttu-id="d6344-118">此外，會議政策可用來控制 Teams 會議的音訊和視音訊設定，例如文字記錄、雲端錄製和 IP 音訊/視視。</span><span class="sxs-lookup"><span data-stu-id="d6344-118">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![會議策略的螢幕擷取畫面。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="d6344-120">適用於教育的 Teams</span><span class="sxs-lookup"><span data-stu-id="d6344-120">Teams for Education</span></span>

<span data-ttu-id="d6344-121">您也可以使用 Teams [教育政策精靈](easy-policy-setup-edu.md) ，輕鬆設定和管理學習環境的政策。</span><span class="sxs-lookup"><span data-stu-id="d6344-121">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Teams 教育政策精靈的螢幕擷取畫面。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="d6344-123">政策類型</span><span class="sxs-lookup"><span data-stu-id="d6344-123">Types of policies</span></span>

<span data-ttu-id="d6344-124">您可以使用 Microsoft Teams 管理下列政策。</span><span class="sxs-lookup"><span data-stu-id="d6344-124">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="d6344-125">策略類型</span><span class="sxs-lookup"><span data-stu-id="d6344-125">Policy type</span></span> | <span data-ttu-id="d6344-126">說明</span><span class="sxs-lookup"><span data-stu-id="d6344-126">Description</span></span>
------------|------------
[<span data-ttu-id="d6344-127">策略套件</span><span class="sxs-lookup"><span data-stu-id="d6344-127">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="d6344-128">Microsoft Teams 中的策略套件是一組預先定義的策略和設定，您可以指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="d6344-128">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="d6344-129">會議原則</span><span class="sxs-lookup"><span data-stu-id="d6344-129">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="d6344-130">會議政策可用來控制組織中使用者排程之會議的會議參與者可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="d6344-130">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="d6344-131">會議政策包含下列主題。</span><span class="sxs-lookup"><span data-stu-id="d6344-131">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="d6344-132">- 音訊和視音訊政策</span><span class="sxs-lookup"><span data-stu-id="d6344-132">- Audio and video policies</span></span><br> <span data-ttu-id="d6344-133">- 內容和螢幕畫面分享政策</span><span class="sxs-lookup"><span data-stu-id="d6344-133">- Content and screen sharing policies</span></span><br> <span data-ttu-id="d6344-134">- 參與者、來賓和存取政策</span><span class="sxs-lookup"><span data-stu-id="d6344-134">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="d6344-135">- 一般政策</span><span class="sxs-lookup"><span data-stu-id="d6344-135">- General policies</span></span>
[<span data-ttu-id="d6344-136">語音和通話政策</span><span class="sxs-lookup"><span data-stu-id="d6344-136">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="d6344-137">語音和通話政策會透過團隊管理這些設定，例如緊急通話、呼叫路由和本機號碼。</span><span class="sxs-lookup"><span data-stu-id="d6344-137">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="d6344-138">應用程式政策</span><span class="sxs-lookup"><span data-stu-id="d6344-138">App policies</span></span>](app-policies.md)| <span data-ttu-id="d6344-139">應用程式策略是用來控制 Microsoft Teams 中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6344-139">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="d6344-140">系統管理員可以允許或封鎖使用者可以安裝的應用程式、將應用程式釘到使用者的 Teams 應用程式欄，以及代表您的使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6344-140">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="d6344-141">訊息原則</span><span class="sxs-lookup"><span data-stu-id="d6344-141">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="d6344-142">訊息策略可控制聊天和頻道功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="d6344-142">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d6344-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6344-143">Related topics</span></span>

* [<span data-ttu-id="d6344-144">在 Microsoft Teams 中管理意見回饋政策</span><span class="sxs-lookup"><span data-stu-id="d6344-144">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="d6344-145">在 Microsoft Teams 中管理團隊政策</span><span class="sxs-lookup"><span data-stu-id="d6344-145">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="d6344-146">在 Microsoft Teams 中設定即時活動</span><span class="sxs-lookup"><span data-stu-id="d6344-146">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="d6344-147">Teams 教育政策與政策套件</span><span class="sxs-lookup"><span data-stu-id="d6344-147">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)
