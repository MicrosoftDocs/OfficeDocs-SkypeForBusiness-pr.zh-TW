---
title: 使用 Microsoft 團隊的網路 planner
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 系統管理員可以瞭解如何使用網路 Planner 來判斷 Microsoft 團隊的網路需求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8c6a59216d1ac04c0e079015aa9de13f8cecb37
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088231"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a><span data-ttu-id="a869a-103">使用 Microsoft 團隊的網路 planner</span><span class="sxs-lookup"><span data-stu-id="a869a-103">Use the Network planner for Microsoft Teams</span></span>

<span data-ttu-id="a869a-104">網路 Planner 是團隊系統管理中心提供的新工具。</span><span class="sxs-lookup"><span data-stu-id="a869a-104">Network Planner is a new tool that is available in the Teams admin center.</span></span> <span data-ttu-id="a869a-105">您可以前往**Planner**  >  **網路 Planner**找到它。</span><span class="sxs-lookup"><span data-stu-id="a869a-105">It can be found by going to **Planner** > **Network planner**.</span></span> <span data-ttu-id="a869a-106">網路 Planner 只需要幾個步驟，就能協助您決定並組織在整個組織中連線 Microsoft 團隊使用者的網路需求。</span><span class="sxs-lookup"><span data-stu-id="a869a-106">In just a few steps, the Network Planner can help you determine and organize network requirements for connecting Microsoft Teams users across your organization.</span></span> <span data-ttu-id="a869a-107">當您提供您的網路詳細資料和團隊使用量時，網路 Planner 會計算您的網路需求，以便在整個組織的物理位置部署團隊和雲端語音。</span><span class="sxs-lookup"><span data-stu-id="a869a-107">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span>

![網路 planner 的螢幕擷取畫面](media/network-planner.png)

<span data-ttu-id="a869a-109">網路 planner 可讓您：</span><span class="sxs-lookup"><span data-stu-id="a869a-109">Network planner allows you to:</span></span>

- <span data-ttu-id="a869a-110">使用網站與 Microsoft 建議的角色（office 工人、遠端工作人員和團隊房間系統）建立您組織的代表。</span><span class="sxs-lookup"><span data-stu-id="a869a-110">Create representations of your organization using sites and Microsoft recommended personas (office workers, remote workers, and Teams room system).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a869a-111">根據來自團隊最佳使用案例的資料，以及一般使用模式所開發的建議角色。</span><span class="sxs-lookup"><span data-stu-id="a869a-111">The recommended personas were developed based on data from Teams best use scenarios and typical usage patterns.</span></span> <span data-ttu-id="a869a-112">不過，除了三個建議的角色之外，您還可以建立最多三個自訂角色。</span><span class="sxs-lookup"><span data-stu-id="a869a-112">However, you can create up to three custom personas in addition to the three recommended personas.</span></span>

- <span data-ttu-id="a869a-113">產生報告並計算團隊使用量的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="a869a-113">Generate reports and calculate bandwidth requirements for Teams usage.</span></span>

<span data-ttu-id="a869a-114">若要使用網路 planner，您必須是全域系統管理員、團隊服務系統管理員或團隊通訊系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a869a-114">To use Network planner, you must be a Global Administrator, Teams Service Administrator, or Teams Communications Administrator.</span></span>

## <a name="create-a-custom-persona"></a><span data-ttu-id="a869a-115">建立自訂角色</span><span class="sxs-lookup"><span data-stu-id="a869a-115">Create a custom persona</span></span>

<span data-ttu-id="a869a-116">請依照下列步驟來建立自訂角色：</span><span class="sxs-lookup"><span data-stu-id="a869a-116">Follow these steps to create a custom persona:</span></span>

1. <span data-ttu-id="a869a-117">移至 Microsoft 團隊系統管理中心的 [網路 planner]。</span><span class="sxs-lookup"><span data-stu-id="a869a-117">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="a869a-118">在 [**角色**] 索引標籤上，按一下 [ **+ 自訂角色**]。</span><span class="sxs-lookup"><span data-stu-id="a869a-118">On the **Personas** tab, click **+ Custom persona**.</span></span> 

3. <span data-ttu-id="a869a-119">在 [**新增自訂角色**] 窗格中，為新的角色新增名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="a869a-119">In the **New custom persona** pane, add a name and description for the new persona.</span></span>

4. <span data-ttu-id="a869a-120">選取此角色將在組織中使用的許可權。</span><span class="sxs-lookup"><span data-stu-id="a869a-120">Select the permissions that this persona will use within the organization.</span></span>

5. <span data-ttu-id="a869a-121">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a869a-121">Click **Save**.</span></span>

## <a name="build-your-plan"></a><span data-ttu-id="a869a-122">建立您的計畫</span><span class="sxs-lookup"><span data-stu-id="a869a-122">Build your plan</span></span>

<span data-ttu-id="a869a-123">請依照下列步驟開始建立您的網路方案：</span><span class="sxs-lookup"><span data-stu-id="a869a-123">Follow these steps to begin building your network plan:</span></span>

1. <span data-ttu-id="a869a-124">移至 Microsoft 團隊系統管理中心的 [網路 planner]。</span><span class="sxs-lookup"><span data-stu-id="a869a-124">Go to the Network planner in the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="a869a-125">在 [**網路方案**] 索引標籤上，按一下 [**新增網路方案**]。</span><span class="sxs-lookup"><span data-stu-id="a869a-125">On the **Network Plan** tab, click **Add a network plan**.</span></span>

3. <span data-ttu-id="a869a-126">輸入您的網路方案的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="a869a-126">Enter a name and description for your network plan.</span></span> <span data-ttu-id="a869a-127">網路方案會出現在可用方案清單中。</span><span class="sxs-lookup"><span data-stu-id="a869a-127">The network plan will appear in the list of available plans.</span></span>

4. <span data-ttu-id="a869a-128">按一下方案名稱以選取新方案。</span><span class="sxs-lookup"><span data-stu-id="a869a-128">Click the plan name to select the new plan.</span></span>

5. <span data-ttu-id="a869a-129">新增網站以建立貴組織網路設定的表示。</span><span class="sxs-lookup"><span data-stu-id="a869a-129">Add sites to create a representation of your organization's network setup.</span></span>

    <span data-ttu-id="a869a-130">視貴組織的網路而定，您可能會想要使用網站來代表組建、辦公室位置或其他內容。</span><span class="sxs-lookup"><span data-stu-id="a869a-130">Depending on your organization's network, you may want to use sites to represent a building, an office location, or something else.</span></span> <span data-ttu-id="a869a-131">網站可能是由 WAN 連線來允許共用網際網路和/或 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="a869a-131">Sites might be connected by a WAN to allow sharing of internet and/or PSTN connections.</span></span> <span data-ttu-id="a869a-132">為了獲得最佳結果，請先建立擁有本機連線的網站，然後再建立可遠端連線至網際網路或 PSTN 的網站。</span><span class="sxs-lookup"><span data-stu-id="a869a-132">For best results, create sites with local connections before you create sites that remotely connect to the internet or PSTN.</span></span>

    <span data-ttu-id="a869a-133">若要建立網站：</span><span class="sxs-lookup"><span data-stu-id="a869a-133">To create a site:</span></span>

    1. <span data-ttu-id="a869a-134">為您的網站新增名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="a869a-134">Add a name and description for your site.</span></span>

    2. <span data-ttu-id="a869a-135">在 [**網路設定**] 底下，新增該網站的網路使用者數量（必要）。</span><span class="sxs-lookup"><span data-stu-id="a869a-135">Under **Network settings**, add the number of network users at that site (required).</span></span>

    3. <span data-ttu-id="a869a-136">新增網路詳細資料： WAN 啟用、WAN 容量、網際網路出口（**本機**或**遠端**）和 PSTN 出口（無、本機或遠端）。</span><span class="sxs-lookup"><span data-stu-id="a869a-136">Add network details: WAN-enabled, WAN capacity, internet egress (**Local** or **Remote**), and PSTN egress (none, local, or remote).</span></span>

      > [!NOTE]
      > <span data-ttu-id="a869a-137">您必須新增 WAN 和網際網路容量數位，才能查看您產生報告時的特定頻寬建議。</span><span class="sxs-lookup"><span data-stu-id="a869a-137">You must add WAN and internet capacity numbers to see specific bandwidth recommendations when you generate a report.</span></span>

    4. <span data-ttu-id="a869a-138">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a869a-138">Click **Save**.</span></span>

## <a name="create-a-report"></a><span data-ttu-id="a869a-139">建立報表</span><span class="sxs-lookup"><span data-stu-id="a869a-139">Create a report</span></span>

<span data-ttu-id="a869a-140">新增所有網站之後，您可以建立報表，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a869a-140">After you add all sites, you can create a report, as follows.</span></span>

1. <span data-ttu-id="a869a-141">在 [**報表**] 索引標籤上，按一下 [**啟動報表**]。</span><span class="sxs-lookup"><span data-stu-id="a869a-141">On the **Reports** tab, click **Start a report**.</span></span>

2. <span data-ttu-id="a869a-142">針對您建立的每個網站，散佈各個可用角色的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a869a-142">For each site you create, distribute the number of users across the available personas.</span></span> <span data-ttu-id="a869a-143">如果您使用 Microsoft 建議的角色，該數位會自動散佈（80% office worker 和20% 的遠端工作人員）。</span><span class="sxs-lookup"><span data-stu-id="a869a-143">If you use the Microsoft recommended personas, the number will be distributed automatically (80% office worker and 20% remote worker).</span></span>

3. <span data-ttu-id="a869a-144">完成發佈之後，按一下 [**產生報表**]。</span><span class="sxs-lookup"><span data-stu-id="a869a-144">After you complete the distribution, click **Generate report**.</span></span>

    <span data-ttu-id="a869a-145">產生的報告將會顯示幾個不同視圖的頻寬需求，讓您可以清楚地瞭解輸出：</span><span class="sxs-lookup"><span data-stu-id="a869a-145">The generated report will show the bandwidth requirements in several different views so that you can clearly understand the output:</span></span>
    - <span data-ttu-id="a869a-146">含個別計算的表格將會顯示每個允許活動的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="a869a-146">A table with individual calculations will display bandwidth requirements for each permitted activity.</span></span>
    - <span data-ttu-id="a869a-147">[其他] 視圖會以建議顯示整體頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="a869a-147">An additional view will show the overall bandwidth needs with recommendations.</span></span>

4. <span data-ttu-id="a869a-148">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a869a-148">Click **Save**.</span></span> <span data-ttu-id="a869a-149">您可以在報表清單中使用您的報表，以供日後查看。</span><span class="sxs-lookup"><span data-stu-id="a869a-149">Your report will be available on the reports list for later viewing.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a869a-150">範例案例</span><span class="sxs-lookup"><span data-stu-id="a869a-150">Example scenario</span></span>

<span data-ttu-id="a869a-151">如需如何使用網路 planner 設定網路方案並使用這些步驟產生報告的範例，請下載[網路 planner 操作說明版 PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)投影片組（僅提供英文版）。</span><span class="sxs-lookup"><span data-stu-id="a869a-151">For an example of how to use the Network planner to set up a network plan and generate a report using these steps, download the [Network planner How-To PowerPoint deck](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (English only).</span></span>
