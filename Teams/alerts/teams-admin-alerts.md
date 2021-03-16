---
title: Microsoft Teams 監控與警示
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
description: 瞭解 Microsoft Teams 系統管理中心提供的 Teams 通知和通知功能。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819434"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="6a2f1-103">Microsoft Teams 監控與警示</span><span class="sxs-lookup"><span data-stu-id="6a2f1-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="6a2f1-104">Microsoft Teams 的新監控和警示功能可在 Teams 系統管理中心使用。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="6a2f1-105">在 Teams 系統管理中心的 & **通知** 區段下，使用不同的可用規則集來監控 Teams 功能並接收通知。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="6a2f1-106">例如，您可以主動監控 Teams 裝置的健康情況，例如 IP 電話、共同合作條及其他裝置是否意外離線。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="6a2f1-107">您的組織可以使用 Teams 監控和通知執行下列專案：</span><span class="sxs-lookup"><span data-stu-id="6a2f1-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="6a2f1-108">自動管理 Teams 功能</span><span class="sxs-lookup"><span data-stu-id="6a2f1-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="6a2f1-109">如果顯示意外專案，會收到通知。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="6a2f1-110">採取矯正動作，讓事情回到正軌。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="6a2f1-111">如何管理監控和警示</span><span class="sxs-lookup"><span data-stu-id="6a2f1-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="6a2f1-112">您必須是 Microsoft 365 中的全域系統管理員或 Teams 服務系統管理員，才能設定通知規則。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="6a2f1-113">請參閱 [使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md) 以深入瞭解 Teams 系統管理員角色，以及每個系統管理員角色可存取的報告。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="6a2f1-114">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="6a2f1-115">從左側流覽中，選取 **通知&通知**。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="6a2f1-116">從規則中選擇您想要設定 **的規則**。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="6a2f1-117">Teams 監控規則參照</span><span class="sxs-lookup"><span data-stu-id="6a2f1-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="6a2f1-118">我們會新增各種監控功能和組組功能，以持續新增及改善 Teams 監控體驗。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="6a2f1-119">以下是 Teams 系統管理中心目前提供的 Teams 監控規則清單。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="6a2f1-120">規則</span><span class="sxs-lookup"><span data-stu-id="6a2f1-120">Rule</span></span>  |<span data-ttu-id="6a2f1-121">監控功能</span><span class="sxs-lookup"><span data-stu-id="6a2f1-121">Monitoring capability</span></span>|<span data-ttu-id="6a2f1-122">監控哪些專案？</span><span class="sxs-lookup"><span data-stu-id="6a2f1-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="6a2f1-123">裝置健康情況狀態</span><span class="sxs-lookup"><span data-stu-id="6a2f1-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="6a2f1-124">Teams 裝置</span><span class="sxs-lookup"><span data-stu-id="6a2f1-124">Teams Devices</span></span> | <span data-ttu-id="6a2f1-125">如果 Teams 裝置離線，請主動監控這些裝置。</span><span class="sxs-lookup"><span data-stu-id="6a2f1-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
