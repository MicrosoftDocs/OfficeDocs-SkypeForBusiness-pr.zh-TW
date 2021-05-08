---
title: 使用網路規劃工具Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 系統管理員可以瞭解如何使用網路規劃器來判斷網路Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240476"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="23fd5-103">使用網路規劃工具Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23fd5-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="23fd5-104">網路規劃工具是可在系統管理中心Teams工具。</span><span class="sxs-lookup"><span data-stu-id="23fd5-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="23fd5-105">您可以到規劃網路規劃工具  >  **找到它**。</span><span class="sxs-lookup"><span data-stu-id="23fd5-105">It can be found by going to **Planning** > **Network planner**.</span></span> <span data-ttu-id="23fd5-106">在幾個步驟中，網路規劃工具可協助您判斷及組織連接Microsoft Teams使用者的網路需求。</span><span class="sxs-lookup"><span data-stu-id="23fd5-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="23fd5-107">提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。</span><span class="sxs-lookup"><span data-stu-id="23fd5-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![網路規劃工具的螢幕擷取畫面](media/network-planner.png)

<span data-ttu-id="23fd5-109">網路規劃工具可讓您：</span><span class="sxs-lookup"><span data-stu-id="23fd5-109">Network planner allows you to:</span></span>

- <span data-ttu-id="23fd5-110">使用網站和 Microsoft 建議角色建立貴組織的 (辦公室工作人員、遠端工作人員，Teams會議室) 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="23fd5-111">建議的人物角色是根據最佳使用Teams和一般使用模式的資料所開發。</span><span class="sxs-lookup"><span data-stu-id="23fd5-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="23fd5-112">不過，除了三個建議角色之外，您最多可以建立三個自訂角色。</span><span class="sxs-lookup"><span data-stu-id="23fd5-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="23fd5-113">產生報告並計算使用量Teams頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="23fd5-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="23fd5-114">若要使用網路規劃工具，您必須是全域系統管理員、Teams管理員，或Teams管理員。</span><span class="sxs-lookup"><span data-stu-id="23fd5-114">To use Network planner, you must be a Global Administrator, Teams Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="23fd5-115">建立自訂角色</span><span class="sxs-lookup"><span data-stu-id="23fd5-115">Create a custom persona</span></span>

<span data-ttu-id="23fd5-116">請遵循下列步驟建立自訂角色：</span><span class="sxs-lookup"><span data-stu-id="23fd5-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="23fd5-117">請前往系統管理中心Microsoft Teams規劃工具。</span><span class="sxs-lookup"><span data-stu-id="23fd5-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="23fd5-118">在 [**角色」 選項卡** 上，按一下 **[ + 自訂角色。**</span><span class="sxs-lookup"><span data-stu-id="23fd5-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="23fd5-119">在新增 **自訂角色窗格中** ，新增新角色的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="23fd5-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="23fd5-120">選取此角色在組織中使用的許可權。</span><span class="sxs-lookup"><span data-stu-id="23fd5-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="23fd5-121">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="23fd5-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="23fd5-122">建立您的計畫</span><span class="sxs-lookup"><span data-stu-id="23fd5-122">Build your plan</span></span>

<span data-ttu-id="23fd5-123">請遵循下列步驟開始建立您的網路計畫：</span><span class="sxs-lookup"><span data-stu-id="23fd5-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="23fd5-124">請前往系統管理中心Microsoft Teams規劃工具。</span><span class="sxs-lookup"><span data-stu-id="23fd5-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="23fd5-125">在 [ **網路計畫」** 選項卡上，按一下 **[新增網路方案**> 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="23fd5-126">輸入您的網路方案名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="23fd5-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="23fd5-127">網路方案會顯示在可用方案清單中。</span><span class="sxs-lookup"><span data-stu-id="23fd5-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="23fd5-128">按一下計畫名稱以選取新計畫。</span><span class="sxs-lookup"><span data-stu-id="23fd5-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="23fd5-129">新增網站以建立貴組織的網路設定表示。</span><span class="sxs-lookup"><span data-stu-id="23fd5-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="23fd5-130">視貴組織的網路，您可能會想要使用網站來代表建築物、辦公室位置或其他專案。</span><span class="sxs-lookup"><span data-stu-id="23fd5-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="23fd5-131">網站可能由 WAN 連結，以允許共用網際網路和/或 PSTN 連接。</span><span class="sxs-lookup"><span data-stu-id="23fd5-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="23fd5-132">為了獲得最佳結果，在建立遠端連線到網際網路或 PSTN 的網站之前，先建立具有本地連結的網站。</span><span class="sxs-lookup"><span data-stu-id="23fd5-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="23fd5-133">若要建立網站：</span><span class="sxs-lookup"><span data-stu-id="23fd5-133">To create a site:</span></span>

    1. <span data-ttu-id="23fd5-134">為您的網站新增名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="23fd5-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="23fd5-135">在 **網路設定** 下，將該網站的網路使用者數目 () 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="23fd5-136">新增網路詳細資料：啟用 WAN、WAN 容量、網際網路出口 (本地或遠端 **) ，** 以及 PSTN 出口 (無、本地或遠端) 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="23fd5-137">您必須新增 WAN 和網際網路容量號碼，以在產生報表時查看特定的頻寬建議。</span><span class="sxs-lookup"><span data-stu-id="23fd5-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="23fd5-138">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="23fd5-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="23fd5-139">建立報表</span><span class="sxs-lookup"><span data-stu-id="23fd5-139">Create a report</span></span>

<span data-ttu-id="23fd5-140">新增所有網站之後，您可以建立報表，如下所示。</span><span class="sxs-lookup"><span data-stu-id="23fd5-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="23fd5-141">在 [ **報表>** 選項卡上，按一下 **[開始報表>**。</span><span class="sxs-lookup"><span data-stu-id="23fd5-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="23fd5-142">針對您建立的每個網站，將使用者人數分散到可用的角色。</span><span class="sxs-lookup"><span data-stu-id="23fd5-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="23fd5-143">如果您使用 Microsoft 建議的人物角色，系統會自動 (80% 的 office 員工和 20% 的遠端) 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="23fd5-144">完成發佈後，按一下 [ **產生報表**> 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="23fd5-145">產生的報表會以數種不同的視圖顯示頻寬需求，以便清楚瞭解輸出：</span><span class="sxs-lookup"><span data-stu-id="23fd5-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="23fd5-146">包含個別計算的表格會顯示每個允許活動的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="23fd5-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="23fd5-147">另一個視圖會顯示整體頻寬需求與建議。</span><span class="sxs-lookup"><span data-stu-id="23fd5-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="23fd5-148">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="23fd5-148">Click **Save**.</span></span> <span data-ttu-id="23fd5-149">您的報表會列于報表清單上，以便日後檢視。</span><span class="sxs-lookup"><span data-stu-id="23fd5-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="23fd5-150">範例案例</span><span class="sxs-lookup"><span data-stu-id="23fd5-150">Example scenario</span></span>

<span data-ttu-id="23fd5-151">若要瞭解如何使用網路規劃工具設定網路計畫，並使用這些步驟產生報表的範例，請下載網路規劃工具How-To PowerPoint組 (英文[](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)) 。</span><span class="sxs-lookup"><span data-stu-id="23fd5-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
