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
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: 瞭解如何從審核記錄中檢索 Microsoft 團隊資料。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778889"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="9dbf9-103">在 [審核記錄] 中搜尋 Microsoft 團隊中的事件</span><span class="sxs-lookup"><span data-stu-id="9dbf9-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="9dbf9-104">審核記錄可協助您調查跨 Office 365 服務的特定活動。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="9dbf9-105">針對團隊而言，以下是一些經過審核的活動：</span><span class="sxs-lookup"><span data-stu-id="9dbf9-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="9dbf9-106">小組建立</span><span class="sxs-lookup"><span data-stu-id="9dbf9-106">Team creation</span></span>

- <span data-ttu-id="9dbf9-107">小組刪除</span><span class="sxs-lookup"><span data-stu-id="9dbf9-107">Team deletion</span></span>

- <span data-ttu-id="9dbf9-108">已新增頻道</span><span class="sxs-lookup"><span data-stu-id="9dbf9-108">Added channel</span></span>

- <span data-ttu-id="9dbf9-109">已變更設定</span><span class="sxs-lookup"><span data-stu-id="9dbf9-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="9dbf9-110">來自專用通道的審核事件也會記錄為針對團隊和標準通道的活動。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="9dbf9-111">若要查看在 Microsoft 365 中審核之活動的完整清單，請參閱[在 microsoft 365 規範中心搜尋審核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-111">To see the complete list of activities that are audited in Microsoft 365, read [Search the audit log in the Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="9dbf9-112">在團隊中開啟審核</span><span class="sxs-lookup"><span data-stu-id="9dbf9-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="9dbf9-113">您必須先在[安全性 & 合規性中心](https://protection.office.com)開啟審核，然後才能查看審核資料。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="9dbf9-114">如需有關開啟審核的協助，請參閱[開啟或關閉審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-114">For help turning on auditing, read [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dbf9-115">審核資料只能從您開啟 [審計] 的位置使用。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="9dbf9-116">從審核記錄中取得團隊資料</span><span class="sxs-lookup"><span data-stu-id="9dbf9-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="9dbf9-117">若要取得審核記錄，請移至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=855775)。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="9dbf9-118">在 [**搜尋**] 底下，選取 [**審核記錄搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="9dbf9-119">使用 [**搜尋**] 篩選您想要審核的活動、日期和使用者。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="9dbf9-120">將結果匯出至 Excel 以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dbf9-121">審核資料只有在已開啟審核的情況下，才會顯示在審核記錄中。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="9dbf9-122">外部使用者案例</span><span class="sxs-lookup"><span data-stu-id="9dbf9-122">External user scenario</span></span>

<span data-ttu-id="9dbf9-123">從商務角度來看，您可能會想要記住的一個案例，就是將外部使用者新增至您的小組環境。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="9dbf9-124">如果已啟用外部使用者，則監視其目前狀態是一個不錯的主意。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="9dbf9-126">此原則的螢幕擷取畫面可讓您命名原則、根據您的業務需求來設定嚴重性、將其設定為（在此例中為單一活動），然後建立將只會監視非內部使用者的參數，並將此活動限制為 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="9dbf9-127">然後，就可以在活動記錄中查看來自此原則的結果：</span><span class="sxs-lookup"><span data-stu-id="9dbf9-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsExternalUserList.png)

<span data-ttu-id="9dbf9-129">您可以在這裡查看已設定的原則相符的專案，並視需要進行調整，或將結果匯出成在其他地方使用。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="9dbf9-130">成批刪除案例</span><span class="sxs-lookup"><span data-stu-id="9dbf9-130">Mass delete scenario</span></span>

<span data-ttu-id="9dbf9-131">如上述所述，您可以監視刪除情況。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="9dbf9-132">您可以建立可監視大量刪除小組網站的原則：</span><span class="sxs-lookup"><span data-stu-id="9dbf9-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![[原則建立] 頁面的螢幕擷取畫面，其中顯示設定大量小組刪除偵測原則的原則](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="9dbf9-134">如螢幕擷取畫面所示，您可以針對此原則設定許多不同的參數來監視團隊刪除，包括嚴重性、單一或重複動作，以及將此限制為小組和網站刪除的參數。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="9dbf9-135">您可以根據組織的需求，從範本中獨立完成此操作，或者您可能會根據貴組織的需求而建立範本來建立基礎。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="9dbf9-136">建立適用于您企業的原則之後，您就可以在觸發事件時查看活動記錄中的結果：</span><span class="sxs-lookup"><span data-stu-id="9dbf9-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![大量刪除所觸發的事件清單的螢幕擷取畫面](media/TeamsMassDeleteList.png)

<span data-ttu-id="9dbf9-138">您可以篩選到已設定的原則，以查看該原則的結果。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="9dbf9-139">如果您在活動記錄中取得的結果不滿意（可能是您看到許多結果，或是根本沒有反應），這可能會協助您微調查詢，使其更符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="9dbf9-140">影片： TechTip：在團隊中使用審核記錄搜尋</span><span class="sxs-lookup"><span data-stu-id="9dbf9-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="9dbf9-141">加入 Ansuman Acharya （一種小組的程式管理員），他示範如何在 Office 365 安全 & 規範中心中執行審核記錄搜尋小組。</span><span class="sxs-lookup"><span data-stu-id="9dbf9-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
