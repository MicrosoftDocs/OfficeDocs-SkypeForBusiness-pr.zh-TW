---
title: Lync Server 2013：設定影片範例案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="357e7-102">設定 Lync Server 2013 的影片範例案例</span><span class="sxs-lookup"><span data-stu-id="357e7-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="357e7-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="357e7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="357e7-104">Lync 2013 新增了支援 1920 x 1080 完整高清（HD）影片和圖庫視圖影片的新影片功能。</span><span class="sxs-lookup"><span data-stu-id="357e7-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="357e7-105">以客戶資料為基礎的度量單位顯示典型的影片頻寬只有與 Lync 2010 稍有增加，但由於完整的 HD 支援而增加了最大的影片頻寬，所以請參閱[Lync Server 2013 中媒體流量需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)的「媒體流量網路使用量」一節。</span><span class="sxs-lookup"><span data-stu-id="357e7-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="357e7-106">因此，系統管理員可能會想要限制特定使用者的影片頻寬（例如分支辦公室中網路容量較低的使用者），並協助確保其他使用者可能獲得最佳的影片品質（例如主管）。</span><span class="sxs-lookup"><span data-stu-id="357e7-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="357e7-107">下表提供針對不同網路容量配置影片的建議設定清單。</span><span class="sxs-lookup"><span data-stu-id="357e7-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="357e7-108">這些設定會限制部分使用者案例傳送和接收較高解析度的影片（請參閱最右邊的資料行）。</span><span class="sxs-lookup"><span data-stu-id="357e7-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="357e7-109">由於最大的接收網路頻寬不足，因此 [最小值] 設定將導致圖庫影片無法使用。</span><span class="sxs-lookup"><span data-stu-id="357e7-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="357e7-110">建議的影片設定</span><span class="sxs-lookup"><span data-stu-id="357e7-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="357e7-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="357e7-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="357e7-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="357e7-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="357e7-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="357e7-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="357e7-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="357e7-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="357e7-115">預期的影片解析度以取得良好品質的影片</span><span class="sxs-lookup"><span data-stu-id="357e7-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="357e7-116">大</span><span class="sxs-lookup"><span data-stu-id="357e7-116">Best</span></span></p></td>
<td><p><span data-ttu-id="357e7-117">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-117">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-118">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-118">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-119">8000</span><span class="sxs-lookup"><span data-stu-id="357e7-119">8000</span></span></p></td>
<td><p><span data-ttu-id="357e7-120">8000</span><span class="sxs-lookup"><span data-stu-id="357e7-120">8000</span></span></p></td>
<td><p><span data-ttu-id="357e7-121">對等：高達 1920 x 1080 視頻解析度</span><span class="sxs-lookup"><span data-stu-id="357e7-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="357e7-122">圖庫視圖：高達 2 1920 x 1080 的影片或多個較小的解析度影片</span><span class="sxs-lookup"><span data-stu-id="357e7-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="357e7-123">良好</span><span class="sxs-lookup"><span data-stu-id="357e7-123">Good</span></span></p></td>
<td><p><span data-ttu-id="357e7-124">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-124">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-125">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-125">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-126">2500</span><span class="sxs-lookup"><span data-stu-id="357e7-126">2500</span></span></p></td>
<td><p><span data-ttu-id="357e7-127">2500</span><span class="sxs-lookup"><span data-stu-id="357e7-127">2500</span></span></p></td>
<td><p><span data-ttu-id="357e7-128">對等：高達 1280 x 720 視頻解析度</span><span class="sxs-lookup"><span data-stu-id="357e7-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="357e7-129">圖庫視圖：最高至 5 640 x 360 解析度的影片</span><span class="sxs-lookup"><span data-stu-id="357e7-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="357e7-130">深淺</span><span class="sxs-lookup"><span data-stu-id="357e7-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="357e7-131">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-131">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-132">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-132">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-133">1000</span><span class="sxs-lookup"><span data-stu-id="357e7-133">1000</span></span></p></td>
<td><p><span data-ttu-id="357e7-134">1000</span><span class="sxs-lookup"><span data-stu-id="357e7-134">1000</span></span></p></td>
<td><p><span data-ttu-id="357e7-135">對等：高達 960 x 540 視頻解析度</span><span class="sxs-lookup"><span data-stu-id="357e7-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="357e7-136">圖庫視圖：最高至 5 424 x 240 解析度的影片</span><span class="sxs-lookup"><span data-stu-id="357e7-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="357e7-137">基本</span><span class="sxs-lookup"><span data-stu-id="357e7-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="357e7-138">滿足</span><span class="sxs-lookup"><span data-stu-id="357e7-138">True</span></span></p></td>
<td><p><span data-ttu-id="357e7-139">虛假</span><span class="sxs-lookup"><span data-stu-id="357e7-139">False</span></span></p></td>
<td><p><span data-ttu-id="357e7-140">350</span><span class="sxs-lookup"><span data-stu-id="357e7-140">350</span></span></p></td>
<td><p><span data-ttu-id="357e7-141">350</span><span class="sxs-lookup"><span data-stu-id="357e7-141">350</span></span></p></td>
<td><p><span data-ttu-id="357e7-142">對等：高達 424 x 240 視頻解析度</span><span class="sxs-lookup"><span data-stu-id="357e7-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="357e7-143">圖庫視圖：無法使用</span><span class="sxs-lookup"><span data-stu-id="357e7-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="357e7-144">您可以使用上表中的資訊，為貴組織中的部分使用者部署新的 HD 影片和圖庫，同時為其他人允許不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="357e7-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="357e7-145">在下列範例中，系統管理員會推出僅提供給主管的最高視頻品質的新視頻功能。</span><span class="sxs-lookup"><span data-stu-id="357e7-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="357e7-146">對於在網路容量較低的遠端分支辦公室中的員工，只會部署來自上表的最小設定。</span><span class="sxs-lookup"><span data-stu-id="357e7-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="357e7-147">針對其他所有員工，部署來自上一個資料表的「良好」設定。</span><span class="sxs-lookup"><span data-stu-id="357e7-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="357e7-148">若要將新功能推出給主管，系統管理員會建立名為 ExecutiveVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="357e7-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="357e7-149">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="357e7-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="357e7-150">VideoBitRateKB 已設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="357e7-151">TotalReceiveVideoBitRateKB 已設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="357e7-152">AllowMultiview 已設定為 True</span><span class="sxs-lookup"><span data-stu-id="357e7-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="357e7-153">EnableMultiviewJoin 已設定為 True</span><span class="sxs-lookup"><span data-stu-id="357e7-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="357e7-154">針對分支辦公室中的員工，系統管理員會建立名為 BranchOfficeVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="357e7-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="357e7-155">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="357e7-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="357e7-156">VideoBitRateKB 已設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="357e7-157">TotalReceiveVideoBitRateKB 已設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="357e7-158">AllowMultiview 已設定為 True</span><span class="sxs-lookup"><span data-stu-id="357e7-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="357e7-159">EnableMultiviewJoin 已設定為 False</span><span class="sxs-lookup"><span data-stu-id="357e7-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="357e7-160">對於其他所有員工，系統管理員會建立名為 StandardVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="357e7-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="357e7-161">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="357e7-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="357e7-162">VideoBitRateKB 已設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="357e7-163">TotalReceiveVideoBitRateKB 已設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="357e7-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="357e7-164">AllowMultiview 已設定為 True</span><span class="sxs-lookup"><span data-stu-id="357e7-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="357e7-165">EnableMultiviewJoin 已設定為 True</span><span class="sxs-lookup"><span data-stu-id="357e7-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="357e7-166">系統管理員會將會議原則指派給使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="357e7-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="357e7-167">ExecutiveVideo 會議原則已指派給主管人員。</span><span class="sxs-lookup"><span data-stu-id="357e7-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="357e7-168">BranchOfficeVideo 會議原則會指派給分支機搆中的所有員工。</span><span class="sxs-lookup"><span data-stu-id="357e7-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="357e7-169">StandardVideo 會議原則會指派給其他所有員工。</span><span class="sxs-lookup"><span data-stu-id="357e7-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="357e7-170">這些會議原則指派會產生下列使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="357e7-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="357e7-171">所有由任何使用者支援圖庫視圖組織的會議，但分支機搆中的員工無法體驗圖庫視圖。</span><span class="sxs-lookup"><span data-stu-id="357e7-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="357e7-172">對於任何二方或多方會議，主管都可以傳送 1920 x 1080 完整的 HD 影片（如果其硬體和網路連結支援），而且可以在其他參與者用戶端支援它的地方收到 1920 x 1080 完整 HD 影片。</span><span class="sxs-lookup"><span data-stu-id="357e7-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="357e7-173">非主管人員在其雙方或多方會議中與主管相比，不會有較低解析度的員工，但仍能取得良好的解析度。</span><span class="sxs-lookup"><span data-stu-id="357e7-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="357e7-174">當 Lync 顯示預設的影片視窗大小時，分支辦公室中的員工就能在兩方通話中取得良好的影片品質;不過，如果 Lync 視窗已最大化至全螢幕，影片解析度就不會增加。</span><span class="sxs-lookup"><span data-stu-id="357e7-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="357e7-175">對於多方會議，分支辦公室中的員工只會看到一個 [活動中的影片]。</span><span class="sxs-lookup"><span data-stu-id="357e7-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

