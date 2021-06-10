---
title: 使用Teams管理
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解Teams政策。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574182"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="e8723-103">使用Teams管理</span><span class="sxs-lookup"><span data-stu-id="e8723-103">Manage Teams with policies</span></span>

<span data-ttu-id="e8723-104">策略是管理系統管理的重要Teams。</span><span class="sxs-lookup"><span data-stu-id="e8723-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="e8723-105">使用本文流覽如何使用策略來為貴組織帶來好處。</span><span class="sxs-lookup"><span data-stu-id="e8723-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="e8723-106">您用於策略的</span><span class="sxs-lookup"><span data-stu-id="e8723-106">What you use policies for</span></span>

<span data-ttu-id="e8723-107">策略是用來在貴組織中完成跨不同領域的許多工作，例如訊息、會議和應用程式。</span><span class="sxs-lookup"><span data-stu-id="e8723-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="e8723-108">您可以執行一些操作，包括允許使用者在團隊頻道中排程會議、讓使用者編輯已送出的郵件，以及控制使用者是否可以將應用程式釘Teams應用程式欄。</span><span class="sxs-lookup"><span data-stu-id="e8723-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="e8723-109">如何指派策略</span><span class="sxs-lookup"><span data-stu-id="e8723-109">How to assign policies</span></span>

<span data-ttu-id="e8723-110">您可以根據貴組織嘗試完成的工作，以多種方式指派策略。</span><span class="sxs-lookup"><span data-stu-id="e8723-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="e8723-111">您可以在系統管理中心進行Teams作業。</span><span class="sxs-lookup"><span data-stu-id="e8723-111">You can make and view assignments in the Teams admin center.</span></span>

![群群組原則作業的螢幕擷取畫面。](media/group-policy-assignment.png)

<span data-ttu-id="e8723-113">深入瞭解如何在這裡指派 [策略](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e8723-113">Learn more about assigning policies [here](policy-assignment-overview.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="e8723-114">如何管理原則</span><span class="sxs-lookup"><span data-stu-id="e8723-114">How to manage policies</span></span>

<span data-ttu-id="e8723-115">使用系統管理中心Microsoft Teams使用[PowerShell 管理原則](./teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e8723-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="e8723-116">例如，應用程式設定策略可以允許使用者上傳自訂應用程式、代表使用者安裝應用程式，以及將應用程式釘Teams欄。</span><span class="sxs-lookup"><span data-stu-id="e8723-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="e8723-117">這些策略在系統管理中心Teams中。</span><span class="sxs-lookup"><span data-stu-id="e8723-117">These policies are configured in the Teams admin center.</span></span>

![應用程式設定策略的螢幕擷取畫面。](media/app-setup-policy.png)

<span data-ttu-id="e8723-119">此外，會議策略可用來控制會議中的音訊和視Teams設定，例如文字翻譯、雲端錄製和 IP 音訊/視像。</span><span class="sxs-lookup"><span data-stu-id="e8723-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![會議策略的螢幕擷取畫面。](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="e8723-121">適用於教育的 Teams</span><span class="sxs-lookup"><span data-stu-id="e8723-121">Teams for Education</span></span>

<span data-ttu-id="e8723-122">您也可以使用教育Teams精靈[](easy-policy-setup-edu.md)，輕鬆設定和管理學習環境的政策。</span><span class="sxs-lookup"><span data-stu-id="e8723-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![教育Teams精靈的螢幕擷取畫面。](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="e8723-124">政策類型</span><span class="sxs-lookup"><span data-stu-id="e8723-124">Types of policies</span></span>

<span data-ttu-id="e8723-125">下列政策可以使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e8723-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="e8723-126">策略類型</span><span class="sxs-lookup"><span data-stu-id="e8723-126">Policy type</span></span> | <span data-ttu-id="e8723-127">描述</span><span class="sxs-lookup"><span data-stu-id="e8723-127">Description</span></span>
------------|------------
[<span data-ttu-id="e8723-128">策略套件</span><span class="sxs-lookup"><span data-stu-id="e8723-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="e8723-129">其中一個Microsoft Teams套件是一組預先定義的策略和設定，您可以指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="e8723-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="e8723-130">會議原則</span><span class="sxs-lookup"><span data-stu-id="e8723-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="e8723-131">會議策略是用來控制貴組織中使用者排程會議之會議參與者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="e8723-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="e8723-132">會議政策包含下列主題。</span><span class="sxs-lookup"><span data-stu-id="e8723-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="e8723-133">- 音訊和視音訊政策</span><span class="sxs-lookup"><span data-stu-id="e8723-133">- Audio and video policies</span></span><br> <span data-ttu-id="e8723-134">- 內容和螢幕畫面共用政策</span><span class="sxs-lookup"><span data-stu-id="e8723-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="e8723-135">- 參與者、來賓和存取政策</span><span class="sxs-lookup"><span data-stu-id="e8723-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="e8723-136">- 一般政策</span><span class="sxs-lookup"><span data-stu-id="e8723-136">- General policies</span></span>
[<span data-ttu-id="e8723-137">語音和通話政策</span><span class="sxs-lookup"><span data-stu-id="e8723-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="e8723-138">語音和通話政策會透過團隊管理這些設定，例如緊急通話、呼叫路由和本機號碼。</span><span class="sxs-lookup"><span data-stu-id="e8723-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="e8723-139">應用程式政策</span><span class="sxs-lookup"><span data-stu-id="e8723-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="e8723-140">應用程式策略用於控制應用程式Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="e8723-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="e8723-141">系統管理員可以允許或封鎖使用者可以安裝的應用程式、將應用程式釘Teams使用者的應用程式欄，以及代表使用者安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="e8723-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="e8723-142">訊息原則</span><span class="sxs-lookup"><span data-stu-id="e8723-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="e8723-143">訊息策略可控制聊天和頻道功能的可用性。</span><span class="sxs-lookup"><span data-stu-id="e8723-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8723-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="e8723-144">Related topics</span></span>

* [<span data-ttu-id="e8723-145">在 Teams 中指派Teams - 開始使用</span><span class="sxs-lookup"><span data-stu-id="e8723-145">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
* [<span data-ttu-id="e8723-146">管理意見Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8723-146">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="e8723-147">管理團隊Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e8723-147">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="e8723-148">在 Microsoft Teams 中設定即時活動</span><span class="sxs-lookup"><span data-stu-id="e8723-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="e8723-149">Teams教育政策與政策套件</span><span class="sxs-lookup"><span data-stu-id="e8723-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)