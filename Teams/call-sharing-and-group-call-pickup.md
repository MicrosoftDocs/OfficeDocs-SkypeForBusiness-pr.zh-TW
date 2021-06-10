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
description: 通話共用和群組呼叫代答功能可讓使用者與同事共用來電，讓使用者可以在使用者無法使用時接聽來電。
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717834"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="4c367-103">通話共用和群組呼叫代答Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c367-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="4c367-104">通話共用和群組呼叫代答功能Microsoft Teams讓使用者與同事共用來電，讓同事可以接聽使用者無法使用時發生的通話。</span><span class="sxs-lookup"><span data-stu-id="4c367-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="4c367-105">群組呼叫代答對收件者的干擾程度較其他通話共用 (例如呼叫轉轉或同時撥打) 較少，因為使用者可以設定想要透過 Teams App) 中的音訊和視覺通知、僅視覺或橫幅收到來電通知的方式 (，而且他們可以決定是否要接聽。</span><span class="sxs-lookup"><span data-stu-id="4c367-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="4c367-106">若要與其他人共用通話，使用者會建立通話群組，並新增想要共用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c367-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="4c367-107">接著，他們選擇同時響鈴或轉場設定。</span><span class="sxs-lookup"><span data-stu-id="4c367-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="4c367-108">請參閱[呼叫轉譯和同時撥打Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4c367-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="4c367-109">請注意，行動裝置只有在設定為橫幅和鈴聲時，才能收到通知。</span><span class="sxs-lookup"><span data-stu-id="4c367-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c367-110">使用者、通話群組擁有者和通話群組的成員必須進入Teams模式。</span><span class="sxs-lookup"><span data-stu-id="4c367-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="4c367-111">有關部署模式Teams詳細資料，請參閱瞭解[Microsoft Teams商務用 Skype及](teams-and-skypeforbusiness-coexistence-and-interoperability.md)互通性</span><span class="sxs-lookup"><span data-stu-id="4c367-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="4c367-112">需要授權</span><span class="sxs-lookup"><span data-stu-id="4c367-112">License required</span></span>

<span data-ttu-id="4c367-113">使用者必須獲得授權Microsoft Teams 電話系統，才能設定及使用通話共用和群組呼叫代答。</span><span class="sxs-lookup"><span data-stu-id="4c367-113">Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="4c367-114">有關授權模型的其他詳細資料[，請參閱以下](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)說明您取得電話系統。</span><span class="sxs-lookup"><span data-stu-id="4c367-114">For additional details on the licensing model, see [Here's what you get with Phone System](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="4c367-115">設定群組通話代答</span><span class="sxs-lookup"><span data-stu-id="4c367-115">Configure group call pickup</span></span>

<span data-ttu-id="4c367-116">若要設定群組呼叫代答，使用者會先設定通話群組 (這與安全性群組或 Microsoft 365 群組) 不同，然後新增想要共用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="4c367-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="4c367-117">接著，他們選擇同時撥打或呼叫呼叫前轉設定。</span><span class="sxs-lookup"><span data-stu-id="4c367-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="4c367-118">如要詳細資訊和逐步程式，請參閱在 Teams 中呼叫轉[Teams。](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="4c367-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="4c367-119">通話群組建立和通知喜好設定是使用者導向的功能;系統管理員不需要為使用者設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="4c367-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="4c367-120">無法從安全性群組或群組建立Microsoft 365群組;它們必須在 Teams 中Teams。</span><span class="sxs-lookup"><span data-stu-id="4c367-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="4c367-121">系統管理員應透過使用者的 **TeamsCallingPolicy AllowCallGroups 設定啟用** 通話群組。</span><span class="sxs-lookup"><span data-stu-id="4c367-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="4c367-122">系統管理員也可以透過系統管理Teams啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="4c367-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="4c367-123">此外，已設定的使用者也可以直接透過用戶端設定其通話群組。</span><span class="sxs-lookup"><span data-stu-id="4c367-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="4c367-124">系統管理員或使用者無法彼此封鎖該組Teams，但系統管理入口網站Teams用戶端應該在這兩個地方正確顯示此關係。</span><span class="sxs-lookup"><span data-stu-id="4c367-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="4c367-125">重要：當系統管理員在使用者 (開啟通話群組後關閉通話群組，且呼叫群組關係已) 時，系統管理員必須清除 Teams 系統管理中心中的使用者的通話群組關係，以避免不正確的通話路由。</span><span class="sxs-lookup"><span data-stu-id="4c367-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="4c367-126">限制</span><span class="sxs-lookup"><span data-stu-id="4c367-126">Limitations</span></span>

<span data-ttu-id="4c367-127">每個已配置的通話群組最多可以有 25 個使用者或 32，768 個字元。</span><span class="sxs-lookup"><span data-stu-id="4c367-127">Each configured call group can have a maximum of 25 users or 32,768 characters.</span></span> 

## <a name="more-information"></a><span data-ttu-id="4c367-128">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4c367-128">More information</span></span>

[<span data-ttu-id="4c367-129">呼叫轉譯和同時撥打Teams</span><span class="sxs-lookup"><span data-stu-id="4c367-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
