---
title: 通話共用和群組來電接聽
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: 通話共用和群組通話挑選讓使用者與同事共用來電，以便在使用者無法使用時，可以捕獲通話。
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620718"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="466c7-103">在 Microsoft 團隊中呼叫共用與群組通話挑選</span><span class="sxs-lookup"><span data-stu-id="466c7-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="466c7-104">Microsoft 團隊的呼叫共用與群組呼叫功能可讓使用者與同事共用來電，讓同事可以接聽使用者無法使用的通話。</span><span class="sxs-lookup"><span data-stu-id="466c7-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="466c7-105">群組呼叫對於 (收件者的電話與其他形式的呼叫共用 (例如來電轉接或同時撥打) ，因為使用者可以設定如何在 [小組] 應用程式) 中，透過音訊和視覺通知、僅限 visual 或橫幅，決定是否要回復。</span><span class="sxs-lookup"><span data-stu-id="466c7-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="466c7-106">若要與其他人共用通話，使用者可以建立通話群組，並新增他們要與其通話共用的使用者。</span><span class="sxs-lookup"><span data-stu-id="466c7-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="466c7-107">然後，選擇同時撥打或轉寄設定。</span><span class="sxs-lookup"><span data-stu-id="466c7-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="466c7-108">如需詳細資訊，請參閱 [在小組中來電轉接及同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) 。</span><span class="sxs-lookup"><span data-stu-id="466c7-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="466c7-109">請注意，行動裝置只會在設定為橫幅與鈴聲時收到通知。</span><span class="sxs-lookup"><span data-stu-id="466c7-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="466c7-110">使用者、通話群組擁有者，以及通話群組的成員，都必須在 [只有小組] 部署模式中。</span><span class="sxs-lookup"><span data-stu-id="466c7-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="466c7-111">如需有關團隊部署模式的詳細資訊，請參閱 [瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="466c7-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="466c7-112">需要授權</span><span class="sxs-lookup"><span data-stu-id="466c7-112">License required</span></span>

<span data-ttu-id="466c7-113">使用者必須是啟用企業語音，才能設定及使用通話共用和群組通話。</span><span class="sxs-lookup"><span data-stu-id="466c7-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="466c7-114">如需授權模型的其他詳細資料，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="466c7-114">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="466c7-115">設定群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="466c7-115">Configure group call pickup</span></span>

<span data-ttu-id="466c7-116">若要設定 [群組呼叫挑選]，使用者必須先設定通話群組 (這與安全群組或 Microsoft 365 群組) 不一樣，然後新增他們想要與其共用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="466c7-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="466c7-117">然後，選擇 [同時撥打] 或 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="466c7-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="466c7-118">如需詳細資訊和逐步程式，請參閱 [在小組中來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="466c7-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="466c7-119">通話群組建立和通知喜好設定是使用者驅動的功能;系統管理員不需要為使用者設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="466c7-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="466c7-120">無法從安全性群組或 Microsoft 365 群組建立通話群組;它們必須在 [團隊] 中建立。</span><span class="sxs-lookup"><span data-stu-id="466c7-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="466c7-121">系統管理員應該透過使用者的 [ **TeamsCallingPolicy AllowCallGroups** ] 設定來啟用呼叫群組。</span><span class="sxs-lookup"><span data-stu-id="466c7-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="466c7-122">系統管理員也可以透過 [團隊管理入口網站] 啟用此。</span><span class="sxs-lookup"><span data-stu-id="466c7-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="466c7-123">此外，已設定的使用者也可以直接透過用戶端設定通話群組。</span><span class="sxs-lookup"><span data-stu-id="466c7-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="466c7-124">系統管理員或使用者不能封鎖彼此的設定，但是團隊管理員入口網站和團隊用戶端應該在這兩個位置中正確顯示這種關聯性。</span><span class="sxs-lookup"><span data-stu-id="466c7-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="466c7-125">重要：當系統管理員開啟 (使用者的呼叫群組，且呼叫群組關聯已設定) 之後，系統管理員必須清除小組系統管理中心中的使用者的通話群組關聯，以避免呼叫路由不正確。</span><span class="sxs-lookup"><span data-stu-id="466c7-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="466c7-126">有限</span><span class="sxs-lookup"><span data-stu-id="466c7-126">Limitations</span></span>

<span data-ttu-id="466c7-127">租使用者最多可以包含32768呼叫群組。</span><span class="sxs-lookup"><span data-stu-id="466c7-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="466c7-128">每個通話群組中最多可以有25個使用者。</span><span class="sxs-lookup"><span data-stu-id="466c7-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="466c7-129">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="466c7-129">More information</span></span>

[<span data-ttu-id="466c7-130">在小組中來電轉接和同時撥打</span><span class="sxs-lookup"><span data-stu-id="466c7-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
