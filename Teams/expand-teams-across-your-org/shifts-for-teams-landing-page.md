---
title: Teams 中的 Shifts
description: 取得您設定及管理班次所需的系統管理指南，此為排程管理工具，Teams。
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 889c3f4149489f6bcea44acde93d897a7f2e50e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092551"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="4c244-103">Teams 中的 Shifts</span><span class="sxs-lookup"><span data-stu-id="4c244-103">Shifts for Teams</span></span>

<span data-ttu-id="4c244-104">Teams為貴組織的前線工作人員提供有效溝通和共同合作所需的工具。</span><span class="sxs-lookup"><span data-stu-id="4c244-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="4c244-105">本文將說明如何設定和管理。</span><span class="sxs-lookup"><span data-stu-id="4c244-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="4c244-106">在作業中班次並使用排程Teams。</span><span class="sxs-lookup"><span data-stu-id="4c244-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="4c244-107">為貴組織設定及管理班次</span><span class="sxs-lookup"><span data-stu-id="4c244-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![工作檢查清單-規劃-團隊](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="4c244-109">**[管理貴組織的班次](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span><span class="sxs-lookup"><span data-stu-id="4c244-109">**[Manage Shifts in your organization](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span></span> |![設計](../media/Help-small.svg)  | <span data-ttu-id="4c244-111">**[前線員工班次說明](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="4c244-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="4c244-112">移轉延伸線</span><span class="sxs-lookup"><span data-stu-id="4c244-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![Api](../media/api-small.svg) | <span data-ttu-id="4c244-114">**[移Graph API](/graph/api/resources/shift?view=graph-rest-1.0)** 移轉Graph API 讓您將 Shifts 資料與外部員工管理系統整合。</span><span class="sxs-lookup"><span data-stu-id="4c244-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="4c244-115">您可以在後端彈性地建立自訂的 Shifts 體驗，同時為使用者提供豐富的前端體驗，Teams。</span><span class="sxs-lookup"><span data-stu-id="4c244-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![Api](../media/api-small.svg) | <span data-ttu-id="4c244-117">**[員工管理整合](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** 如果您使用的是協力廠商員工管理系統 ，例如 Kronos 和 JDA，用於排程、時間和出勤，您可以透過 Shifts Graph API 和 SDK 與開放來源整合，直接與 Shifts 整合。</span><span class="sxs-lookup"><span data-stu-id="4c244-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![Api](../media/process-flow-teams-small.svg) | <span data-ttu-id="4c244-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate可讓您從 Shifts 中取資訊，並與其他 App 建立自訂工作流程，並大規模執行作業。</span><span class="sxs-lookup"><span data-stu-id="4c244-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="4c244-120">使用幾乎不執行任何程式碼來自動化重要程式。</span><span class="sxs-lookup"><span data-stu-id="4c244-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="4c244-121">觸發程式與範本支援各種案例，例如，在不需要主管核准時，為輪班要求啟用自動核准。</span><span class="sxs-lookup"><span data-stu-id="4c244-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="4c244-122">精選訓練</span><span class="sxs-lookup"><span data-stu-id="4c244-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![箭頭-向右-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="4c244-124">影片：什麼是 Shifts？</span><span class="sxs-lookup"><span data-stu-id="4c244-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![時鐘團隊](../media/clock-teams-small.svg)  |  [<span data-ttu-id="4c244-126">影片：什麼是 Shifts？</span><span class="sxs-lookup"><span data-stu-id="4c244-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![區塊團隊](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="4c244-128">影片：管理班次排程</span><span class="sxs-lookup"><span data-stu-id="4c244-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |