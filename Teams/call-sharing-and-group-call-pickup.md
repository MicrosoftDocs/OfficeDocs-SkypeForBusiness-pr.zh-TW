---
title: 在 Microsoft 團隊中呼叫共用與群組通話挑選
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 通話共用和群組通話挑選讓使用者與同事共用來電, 以便在使用者無法使用時, 可以捕獲通話。
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182271"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="24988-103">在 Microsoft 團隊中呼叫共用與群組通話挑選</span><span class="sxs-lookup"><span data-stu-id="24988-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="24988-104">Microsoft 團隊的呼叫共用與群組呼叫功能可讓使用者與同事共用來電, 讓同事可以接聽使用者無法使用的通話。</span><span class="sxs-lookup"><span data-stu-id="24988-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="24988-105">群組通話與其他通話共用形式 (例如來電轉接或同時撥打) 不會對收件者造成中斷影響, 因為使用者可以設定接收共用通話的通知方式 (透過音訊和視覺通知、僅限 visual)。或 [小組] 應用程式中的 [橫幅], 他們可以決定是否要回復。</span><span class="sxs-lookup"><span data-stu-id="24988-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="24988-106">若要與其他人共用通話, 使用者可以建立通話群組, 並新增他們要與其通話共用的使用者。</span><span class="sxs-lookup"><span data-stu-id="24988-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="24988-107">然後, 選擇同時撥打或轉寄設定。</span><span class="sxs-lookup"><span data-stu-id="24988-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="24988-108">如需詳細資訊, 請參閱[在小組中來電轉接及同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="24988-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24988-109">使用者、通話群組擁有者, 以及通話群組的成員, 都必須在 [只有小組] 部署模式中。</span><span class="sxs-lookup"><span data-stu-id="24988-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="24988-110">如需有關團隊部署模式的詳細資訊, 請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="24988-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="24988-111">需要授權</span><span class="sxs-lookup"><span data-stu-id="24988-111">License required</span></span>

<span data-ttu-id="24988-112">使用者必須是啟用企業語音, 才能設定及使用通話共用和群組通話。</span><span class="sxs-lookup"><span data-stu-id="24988-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="24988-113">如需授權模型的其他詳細資料, 請參閱[Microsoft 團隊適用的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="24988-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="24988-114">設定群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="24988-114">Configure group call pickup</span></span>

<span data-ttu-id="24988-115">若要設定 [群組呼叫挑選], 使用者必須先設定通話群組 (這與安全性群組或 Office 365 群組不同), 然後再新增他們要與其共用通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="24988-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="24988-116">然後, 選擇 [同時撥打] 或 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="24988-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="24988-117">如需詳細資訊和逐步程式, 請參閱[在小組中來電轉接和同時撥打](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)。</span><span class="sxs-lookup"><span data-stu-id="24988-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="24988-118">通話群組建立和通知喜好設定是使用者驅動的功能;系統管理員不需要為使用者設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="24988-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="24988-119">無法從安全性群組或 Office 365 群組建立通話群組;它們必須在 [團隊] 中建立。</span><span class="sxs-lookup"><span data-stu-id="24988-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="24988-120">系統管理員應該透過使用者的 [ **TeamsCallingPolicy AllowCallGroups** ] 設定來啟用呼叫群組。</span><span class="sxs-lookup"><span data-stu-id="24988-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="24988-121">系統管理員只能控制此使用者是否可以設定通話群組。</span><span class="sxs-lookup"><span data-stu-id="24988-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="24988-122">一旦將此位設定為 true, 系統管理員就不能防止使用者設定並新增其選擇的通話群組使用者。</span><span class="sxs-lookup"><span data-stu-id="24988-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="24988-123">有限</span><span class="sxs-lookup"><span data-stu-id="24988-123">Limitations</span></span>

<span data-ttu-id="24988-124">租使用者最多可以包含32768呼叫群組。</span><span class="sxs-lookup"><span data-stu-id="24988-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="24988-125">每個通話群組最多可有5個使用者。</span><span class="sxs-lookup"><span data-stu-id="24988-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="24988-126">其他資訊</span><span class="sxs-lookup"><span data-stu-id="24988-126">More information</span></span>

[<span data-ttu-id="24988-127">在小組中來電轉接和同時撥打</span><span class="sxs-lookup"><span data-stu-id="24988-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)