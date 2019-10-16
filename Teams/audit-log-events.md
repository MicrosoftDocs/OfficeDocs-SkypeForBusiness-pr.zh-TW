---
title: 在 [審核記錄] 中搜尋 Microsoft 團隊中的事件
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 瞭解如何從 Office 365 審核記錄中檢索 Microsoft 團隊資料。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d332880756c0173045fc1e5464bd889d0131301
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516728"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="e59ca-103">在 [審核記錄] 中搜尋 Microsoft 團隊中的事件</span><span class="sxs-lookup"><span data-stu-id="e59ca-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="e59ca-104">審核記錄可協助您調查跨 Office 365 服務的特定活動。</span><span class="sxs-lookup"><span data-stu-id="e59ca-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="e59ca-105">針對團隊而言，以下是一些經過審核的活動：</span><span class="sxs-lookup"><span data-stu-id="e59ca-105">For Teams, here are some of the activities that are audited:</span></span>

-   <span data-ttu-id="e59ca-106">小組建立</span><span class="sxs-lookup"><span data-stu-id="e59ca-106">Team creation</span></span>

-   <span data-ttu-id="e59ca-107">小組刪除</span><span class="sxs-lookup"><span data-stu-id="e59ca-107">Team deletion</span></span>

-   <span data-ttu-id="e59ca-108">已新增頻道</span><span class="sxs-lookup"><span data-stu-id="e59ca-108">Added channel</span></span>

-   <span data-ttu-id="e59ca-109">已變更設定</span><span class="sxs-lookup"><span data-stu-id="e59ca-109">Changed setting</span></span>

<span data-ttu-id="e59ca-110">若要查看在 Office 365 中審核之活動的完整清單，請閱讀[在 office 365 安全性 & 合規性中心搜尋審核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="e59ca-110">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="e59ca-111">在團隊中開啟審核</span><span class="sxs-lookup"><span data-stu-id="e59ca-111">Turn on auditing in Teams</span></span>

<span data-ttu-id="e59ca-112">您必須先在**安全性 & 合規性中心**（https://protection.office.com)）中開啟審核，才能查看審核資料。</span><span class="sxs-lookup"><span data-stu-id="e59ca-112">Before you can look at audit data, you have to first turn on auditing in the **Security & Compliance Center**(https://protection.office.com).</span></span> <span data-ttu-id="e59ca-113">如需有關開啟審核的協助，請參閱[開啟或關閉 Office 365 審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="e59ca-113">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e59ca-114">審核資料只能從您開啟 [審計] 的位置使用。</span><span class="sxs-lookup"><span data-stu-id="e59ca-114">Audit data is only available from the point at which you turned on Auditing.</span></span>



## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="e59ca-115">從審核記錄中取得團隊資料</span><span class="sxs-lookup"><span data-stu-id="e59ca-115">Retrieve Teams data from the audit log</span></span>

1.  <span data-ttu-id="e59ca-116">若要取得審核記錄，請移至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="e59ca-116">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="e59ca-117">在 [**搜尋 & 調查**] 底下，選取 [**審核記錄搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="e59ca-117">Under **Search & Investigation**, select **Audit log search**.</span></span>

2.  <span data-ttu-id="e59ca-118">使用 [**搜尋**] 篩選您想要審核的活動、日期和使用者。</span><span class="sxs-lookup"><span data-stu-id="e59ca-118">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3.  <span data-ttu-id="e59ca-119">將結果匯出至 Excel 以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="e59ca-119">Export your results to Excel for further analysis.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e59ca-120">審核資料只有在已開啟審核的情況下，才會顯示在審核記錄中。</span><span class="sxs-lookup"><span data-stu-id="e59ca-120">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="e59ca-121">影片： TechTip：在團隊中使用審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="e59ca-121">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="e59ca-122">加入 Ansuman Acharya （一種小組的程式管理員），他示範如何在 Office 365 安全 & 規範中心中執行審核記錄搜尋小組。</span><span class="sxs-lookup"><span data-stu-id="e59ca-122">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






