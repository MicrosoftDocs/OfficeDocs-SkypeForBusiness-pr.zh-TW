---
title: Microsoft Teams監控與警示
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: 瞭解 Teams系統管理中心提供Microsoft Teams通知和通知功能。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684601"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="fd6b4-103">Microsoft Teams監控和警示</span><span class="sxs-lookup"><span data-stu-id="fd6b4-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="fd6b4-104">系統管理中心提供Microsoft Teams監控和提醒Teams功能。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="fd6b4-105">使用系統管理中心中&通知>區段Teams提供Teams規則集，以監控Teams功能並接收通知。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="fd6b4-106">例如，您可以主動監控 ip 電話、共同Teams等裝置在意外離線時的健康情況。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="fd6b4-107">貴組織可以使用Teams和警示功能執行下列專案：</span><span class="sxs-lookup"><span data-stu-id="fd6b4-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="fd6b4-108">自動管理Teams功能</span><span class="sxs-lookup"><span data-stu-id="fd6b4-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="fd6b4-109">如果顯示意外專案，會收到通知。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="fd6b4-110">採取矯正動作，讓事情回到正軌。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="fd6b4-111">如何管理監控和警示</span><span class="sxs-lookup"><span data-stu-id="fd6b4-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="fd6b4-112">您必須是全域系統管理員Microsoft 365或Teams系統管理員，才能設定通知規則。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="fd6b4-113">請參閱[使用Teams系統管理員角色來管理](../using-admin-roles.md)Teams以深入瞭解Teams管理員角色，以及每個系統管理員角色可以存取的報告。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="fd6b4-114">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="fd6b4-115">從左側流覽中，選取 **通知&通知**。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="fd6b4-116">從規則中選擇您想要設定 **的規則**。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="fd6b4-117">Teams監控規則參照</span><span class="sxs-lookup"><span data-stu-id="fd6b4-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="fd6b4-118">我們會新增各種監控功能和Teams，以持續改善監控體驗。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="fd6b4-119">以下是系統管理中心目前Teams監控規則Teams清單。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="fd6b4-120">規則</span><span class="sxs-lookup"><span data-stu-id="fd6b4-120">Rule</span></span>  |<span data-ttu-id="fd6b4-121">監控功能</span><span class="sxs-lookup"><span data-stu-id="fd6b4-121">Monitoring capability</span></span>|<span data-ttu-id="fd6b4-122">監控哪些專案？</span><span class="sxs-lookup"><span data-stu-id="fd6b4-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="fd6b4-123">裝置健康情況狀態</span><span class="sxs-lookup"><span data-stu-id="fd6b4-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="fd6b4-124">Teams設備</span><span class="sxs-lookup"><span data-stu-id="fd6b4-124">Teams Devices</span></span> | <span data-ttu-id="fd6b4-125">Pro離線時，Teams主動監控這些裝置。</span><span class="sxs-lookup"><span data-stu-id="fd6b4-125">Pro-actively monitor Teams devices if they go offline.</span></span>|