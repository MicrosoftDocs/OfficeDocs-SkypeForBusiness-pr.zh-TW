---
title: 管理內容共用的會議策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 瞭解如何在 Teams 中管理會議策略設定以共用內容。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598713"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="1cb9b-103">會議策略設定 - 內容共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="1cb9b-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="1cb9b-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="1cb9b-105">本文將說明下列與內容共用相關的會議策略設定：</span><span class="sxs-lookup"><span data-stu-id="1cb9b-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="1cb9b-106">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cb9b-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="1cb9b-107">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="1cb9b-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="1cb9b-108">允許外部參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="1cb9b-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="1cb9b-109">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="1cb9b-110">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cb9b-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="1cb9b-111">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cb9b-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="1cb9b-112">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cb9b-112">Screen sharing mode</span></span>

<span data-ttu-id="1cb9b-113">此設定是每個召集人和每個使用者策略的組合。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="1cb9b-114">此設定可控制使用者會議是否允許桌面和視窗共用。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="1cb9b-115">未指派任何策略的會議 (例如匿名、來賓、B2B 和) 繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="1cb9b-116">設定值</span><span class="sxs-lookup"><span data-stu-id="1cb9b-116">Setting value</span></span> |<span data-ttu-id="1cb9b-117">行為</span><span class="sxs-lookup"><span data-stu-id="1cb9b-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1cb9b-118">**整個畫面**</span><span class="sxs-lookup"><span data-stu-id="1cb9b-118">**Entire screen**</span></span>    | <span data-ttu-id="1cb9b-119">會議允許完整桌面共用和應用程式共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="1cb9b-120">**單一應用程式**</span><span class="sxs-lookup"><span data-stu-id="1cb9b-120">**Single application**</span></span>   | <span data-ttu-id="1cb9b-121">會議允許應用程式共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="1cb9b-122">**禁用**</span><span class="sxs-lookup"><span data-stu-id="1cb9b-122">**Disabled**</span></span>     |<span data-ttu-id="1cb9b-123">會議已關閉螢幕畫面共用和應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="1cb9b-124">讓我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-124">Let's look at the following example.</span></span>

|<span data-ttu-id="1cb9b-125">使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-125">User</span></span> |<span data-ttu-id="1cb9b-126">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cb9b-126">Meeting policy</span></span> |<span data-ttu-id="1cb9b-127">螢幕畫面分享模式</span><span class="sxs-lookup"><span data-stu-id="1cb9b-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cb9b-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cb9b-128">Daniela</span></span>  | <span data-ttu-id="1cb9b-129">全域</span><span class="sxs-lookup"><span data-stu-id="1cb9b-129">Global</span></span>   | <span data-ttu-id="1cb9b-130">整個畫面</span><span class="sxs-lookup"><span data-stu-id="1cb9b-130">Entire screen</span></span> |
|<span data-ttu-id="1cb9b-131">艾曼達</span><span class="sxs-lookup"><span data-stu-id="1cb9b-131">Amanda</span></span>   | <span data-ttu-id="1cb9b-132">位置1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cb9b-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="1cb9b-133">禁用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-133">Disabled</span></span> |

<span data-ttu-id="1cb9b-134">Daniela 主持的會議允許會議參與者共用其整個螢幕或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="1cb9b-135">如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定應用程式，因為她的政策設定已停用。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="1cb9b-136">在由 Amanda 主持的會議中，不允許任何人共用其螢幕或單一應用程式，無論指派給他們的螢幕共用模式政策如何。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="1cb9b-137">因此，Daniela 無法共用她的螢幕或單一應用程式在 Amanda 的會議中。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="1cb9b-138">目前，如果使用者使用的是 Google Chrome，他們無法在 Teams 會議中播放影片或共用螢幕畫面。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="1cb9b-139">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="1cb9b-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="1cb9b-140">此設定是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-140">This setting is a per-user policy.</span></span> <span data-ttu-id="1cb9b-141">此設定可控制使用者是否可以將共用桌面或視窗的控制權授予其他會議參與者。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="1cb9b-142">若要提供控制權，請將游標停留在畫面頂端。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="1cb9b-143">如果使用者已開啟此設定，共用會話中的頂端列會顯示提供控制項選項。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![顯示給予控制權選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

<span data-ttu-id="1cb9b-145">如果使用者的設定已關閉，則無法使用提供 **控制項** 選項。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![顯示沒有提供控制權選項的螢幕擷取畫面](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="1cb9b-147">讓我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-147">Let's look at the following example.</span></span>

|<span data-ttu-id="1cb9b-148">使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-148">User</span></span> |<span data-ttu-id="1cb9b-149">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cb9b-149">Meeting policy</span></span>  |<span data-ttu-id="1cb9b-150">允許參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="1cb9b-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cb9b-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cb9b-151">Daniela</span></span>   | <span data-ttu-id="1cb9b-152">全域</span><span class="sxs-lookup"><span data-stu-id="1cb9b-152">Global</span></span>   | <span data-ttu-id="1cb9b-153">已上</span><span class="sxs-lookup"><span data-stu-id="1cb9b-153">On</span></span>       |
|<span data-ttu-id="1cb9b-154">巴別克</span><span class="sxs-lookup"><span data-stu-id="1cb9b-154">Babek</span></span>    | <span data-ttu-id="1cb9b-155">位置1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cb9b-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cb9b-156">關閉</span><span class="sxs-lookup"><span data-stu-id="1cb9b-156">Off</span></span>   |

<span data-ttu-id="1cb9b-157">Daniela 可以將共用桌面或視窗的控制權授予由巴可克組織之會議的其他參與者。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="1cb9b-158">不過，巴別克無法將控制權授予其他參與者。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="1cb9b-159">若要使用 PowerShell 來控制誰可以給予控制權或接受控制權要求，請使用 AllowParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1cb9b-160">若要在共用期間提供並控制共用內容，雙方必須使用 Teams 桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="1cb9b-161">當任一方執行瀏覽器中的 Teams 時，則不支援控制。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="1cb9b-162">這是我們正計畫修正的技術限制所造成。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="1cb9b-163">允許外部參與者提供或要求控制權</span><span class="sxs-lookup"><span data-stu-id="1cb9b-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="1cb9b-164">此設定是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-164">This setting is a per-user policy.</span></span> <span data-ttu-id="1cb9b-165">無論組織是否已為使用者設定此策略，無論會議召集人已設定什麼內容，外部參與者都可以執行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="1cb9b-166">此參數可控制外部參與者是否可以根據共用者在其組織會議政策中設定的內容，獲得控制權或要求控制共用者螢幕。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="1cb9b-167">Teams 會議中的外部參與者可以分類為：</span><span class="sxs-lookup"><span data-stu-id="1cb9b-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="1cb9b-168">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-168">Anonymous user</span></span>
- <span data-ttu-id="1cb9b-169">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-169">Guest users</span></span>  
- <span data-ttu-id="1cb9b-170">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-170">B2B user</span></span>
- <span data-ttu-id="1cb9b-171">聯合使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-171">Federated user</span></span>  

<span data-ttu-id="1cb9b-172">在共用時，聯合使用者是否可以提供控制權給外部使用者，是由允許外部參與者在組織中提供或要求控制權設定所控制。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="1cb9b-173">若要使用 PowerShell 控制外部參與者是否可以提供控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="1cb9b-174">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="1cb9b-175">這是每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-175">This is a per-user policy.</span></span> <span data-ttu-id="1cb9b-176">此設定可控制使用者是否可以共用會議中的 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="1cb9b-177">外部使用者 ，包括匿名、來賓和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1cb9b-178">讓我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-178">Let's look at the following example.</span></span>

|<span data-ttu-id="1cb9b-179">使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-179">User</span></span> |<span data-ttu-id="1cb9b-180">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cb9b-180">Meeting policy</span></span>  |<span data-ttu-id="1cb9b-181">允許 PowerPoint 共用</span><span class="sxs-lookup"><span data-stu-id="1cb9b-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cb9b-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cb9b-182">Daniela</span></span>   | <span data-ttu-id="1cb9b-183">全域</span><span class="sxs-lookup"><span data-stu-id="1cb9b-183">Global</span></span>   | <span data-ttu-id="1cb9b-184">已上</span><span class="sxs-lookup"><span data-stu-id="1cb9b-184">On</span></span>       |
|<span data-ttu-id="1cb9b-185">艾曼達</span><span class="sxs-lookup"><span data-stu-id="1cb9b-185">Amanda</span></span>   | <span data-ttu-id="1cb9b-186">位置1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cb9b-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cb9b-187">關閉</span><span class="sxs-lookup"><span data-stu-id="1cb9b-187">Off</span></span>   |

<span data-ttu-id="1cb9b-188">即使 Amanda 是會議召集人，也無法共用會議中 PowerPoint 的幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="1cb9b-189">即使會議是由 Amanda 組織，Daniela 也可以共用 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="1cb9b-190">Amanda 可以查看會議中其他人共用的 PowerPoint 幻燈片組，即使她無法共用 PowerPoint 幻燈片組。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="1cb9b-191">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cb9b-191">Allow whiteboard</span></span>

<span data-ttu-id="1cb9b-192">此設定是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-192">This setting is a per-user policy.</span></span> <span data-ttu-id="1cb9b-193">此設定可控制使用者是否可以在會議共用白板。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="1cb9b-194">外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1cb9b-195">讓我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-195">Let's look at the following example.</span></span>

|<span data-ttu-id="1cb9b-196">使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-196">User</span></span> |<span data-ttu-id="1cb9b-197">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cb9b-197">Meeting policy</span></span>  |<span data-ttu-id="1cb9b-198">允許白板</span><span class="sxs-lookup"><span data-stu-id="1cb9b-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1cb9b-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cb9b-199">Daniela</span></span>   | <span data-ttu-id="1cb9b-200">全域</span><span class="sxs-lookup"><span data-stu-id="1cb9b-200">Global</span></span>   | <span data-ttu-id="1cb9b-201">已上</span><span class="sxs-lookup"><span data-stu-id="1cb9b-201">On</span></span>       |
|<span data-ttu-id="1cb9b-202">艾曼達</span><span class="sxs-lookup"><span data-stu-id="1cb9b-202">Amanda</span></span>   | <span data-ttu-id="1cb9b-203">位置1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cb9b-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1cb9b-204">關閉</span><span class="sxs-lookup"><span data-stu-id="1cb9b-204">Off</span></span>   |

<span data-ttu-id="1cb9b-205">即使 Amanda 是會議召集人，也無法共用會議中的白板。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="1cb9b-206">即使會議是由 Amanda 組織，Daniela 也可以共用白板。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="1cb9b-207">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cb9b-207">Allow shared notes</span></span>

<span data-ttu-id="1cb9b-208">此設定是每個使用者的策略。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-208">This setting is a per-user policy.</span></span> <span data-ttu-id="1cb9b-209">此設定可控制使用者是否可以在會議建立及共用筆記。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="1cb9b-210">外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="1cb9b-211">目前 **只有** 少於 20 個參與者的會議支援會議筆記選項卡。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="1cb9b-212">讓我們來看看下列範例。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-212">Let's look at the following example.</span></span>

|<span data-ttu-id="1cb9b-213">使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-213">User</span></span> |<span data-ttu-id="1cb9b-214">會議原則</span><span class="sxs-lookup"><span data-stu-id="1cb9b-214">Meeting policy</span></span>  |<span data-ttu-id="1cb9b-215">允許共用筆記</span><span class="sxs-lookup"><span data-stu-id="1cb9b-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1cb9b-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="1cb9b-216">Daniela</span></span>   | <span data-ttu-id="1cb9b-217">全域</span><span class="sxs-lookup"><span data-stu-id="1cb9b-217">Global</span></span>   | <span data-ttu-id="1cb9b-218">已上</span><span class="sxs-lookup"><span data-stu-id="1cb9b-218">On</span></span>       |
|<span data-ttu-id="1cb9b-219">艾曼達</span><span class="sxs-lookup"><span data-stu-id="1cb9b-219">Amanda</span></span>   | <span data-ttu-id="1cb9b-220">位置1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1cb9b-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="1cb9b-221">關閉</span><span class="sxs-lookup"><span data-stu-id="1cb9b-221">Off</span></span> |

<span data-ttu-id="1cb9b-222">Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。</span><span class="sxs-lookup"><span data-stu-id="1cb9b-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="1cb9b-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="1cb9b-223">Related topics</span></span>

- [<span data-ttu-id="1cb9b-224">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="1cb9b-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="1cb9b-225">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="1cb9b-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="1cb9b-226">從使用者移除 RestrictedAnonymousAccess Teams 會議政策</span><span class="sxs-lookup"><span data-stu-id="1cb9b-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
