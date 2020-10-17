---
title: Lync Server 2013：設定影片範例案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf9570f3df344c26da3296904a8394f59f8a907d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516970"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="7fd3a-102">設定 Lync Server 2013 的影片範例案例</span><span class="sxs-lookup"><span data-stu-id="7fd3a-102">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fd3a-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7fd3a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7fd3a-104">Lync 2013 新增影片功能以支援 1920 x 1080 完整高清晰度 (HD) 影片和圖庫 View 影片。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="7fd3a-105">以客戶資料為基礎的度量顯示一般的影片流量只會稍微增加至 Lync 2010，但是影片的最大頻寬已增加由於完整 HD 支援 (如需詳細資訊，請參閱 [Lync Server 2013) 中媒體流量需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md) 的「媒體流量網路使用量」一節。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="7fd3a-106">因此，系統管理員可能會想要限制某些使用者 (的影片頻寬，例如分支辦公室中具有較少網路容量的使用者) 並協助確保其他 (使用者（例如「行政人員) ）的最佳顯示品質。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="7fd3a-107">下表提供設定不同網路容量影片的建議設定清單。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="7fd3a-108">這些設定會限制部分使用者案例傳送和接收較高解析度的影片 (請參閱最右邊的欄) 。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="7fd3a-109">最小設定會導致圖庫影片無法使用，原因是低的接收網路頻寬上限。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="7fd3a-110">建議的影片設定</span><span class="sxs-lookup"><span data-stu-id="7fd3a-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="7fd3a-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="7fd3a-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="7fd3a-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="7fd3a-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="7fd3a-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="7fd3a-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="7fd3a-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="7fd3a-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="7fd3a-115">預期的影片解析度以取得優質影片</span><span class="sxs-lookup"><span data-stu-id="7fd3a-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fd3a-116">最佳</span><span class="sxs-lookup"><span data-stu-id="7fd3a-116">Best</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-117">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-117">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-118">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-118">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-119">8000</span><span class="sxs-lookup"><span data-stu-id="7fd3a-119">8000</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-120">8000</span><span class="sxs-lookup"><span data-stu-id="7fd3a-120">8000</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-121">對等：最高 1920 x 1080 影片解析度</span><span class="sxs-lookup"><span data-stu-id="7fd3a-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="7fd3a-122">圖庫 View：最多 2 1920 x 1080 個影片或多個較小的解析度影片</span><span class="sxs-lookup"><span data-stu-id="7fd3a-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fd3a-123">良好</span><span class="sxs-lookup"><span data-stu-id="7fd3a-123">Good</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-124">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-124">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-125">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-125">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-126">2500</span><span class="sxs-lookup"><span data-stu-id="7fd3a-126">2500</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-127">2500</span><span class="sxs-lookup"><span data-stu-id="7fd3a-127">2500</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-128">對等：最高 1280 x 720 影片解析度</span><span class="sxs-lookup"><span data-stu-id="7fd3a-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="7fd3a-129">圖庫 View：最多 5 640 x 360 解析度的視頻</span><span class="sxs-lookup"><span data-stu-id="7fd3a-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fd3a-130">中</span><span class="sxs-lookup"><span data-stu-id="7fd3a-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-131">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-131">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-132">True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-132">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-133">1000</span><span class="sxs-lookup"><span data-stu-id="7fd3a-133">1000</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-134">1000</span><span class="sxs-lookup"><span data-stu-id="7fd3a-134">1000</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-135">對等：最高 960 x 540 影片解析度</span><span class="sxs-lookup"><span data-stu-id="7fd3a-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="7fd3a-136">圖庫 View：最多 5 424 x 240 解析度的視頻</span><span class="sxs-lookup"><span data-stu-id="7fd3a-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fd3a-137">最小值</span><span class="sxs-lookup"><span data-stu-id="7fd3a-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-138">是</span><span class="sxs-lookup"><span data-stu-id="7fd3a-138">True</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-139">False</span><span class="sxs-lookup"><span data-stu-id="7fd3a-139">False</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-140">350</span><span class="sxs-lookup"><span data-stu-id="7fd3a-140">350</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-141">350</span><span class="sxs-lookup"><span data-stu-id="7fd3a-141">350</span></span></p></td>
<td><p><span data-ttu-id="7fd3a-142">對等：最高 424 x 240 影片解析度</span><span class="sxs-lookup"><span data-stu-id="7fd3a-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="7fd3a-143">圖庫 View：無法使用</span><span class="sxs-lookup"><span data-stu-id="7fd3a-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7fd3a-144">您可以使用上表中的資訊，針對組織中的某些使用者部署新的 HD 影片和畫廊查看影片功能，同時允許其他人使用不同的影片解析度。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="7fd3a-145">在下列範例中，系統管理員只會以最高的視頻品質來推出新的影片功能，僅供主管人員使用。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="7fd3a-146">對於位於網路容量低的遠端分支辦公室員工，只會部署前述表格的最小設定。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="7fd3a-147">對於所有其他員工，會部署上表中的「正確」設定。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="7fd3a-148">若要將新功能推廣至主管，系統管理員會建立名為 ExecutiveVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="7fd3a-149">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="7fd3a-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7fd3a-150">VideoBitRateKB 設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="7fd3a-151">TotalReceiveVideoBitRateKB 設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="7fd3a-152">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7fd3a-153">EnableMultiviewJoin 設定為 True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="7fd3a-154">針對分公司中的員工，系統管理員會建立名為 BranchOfficeVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="7fd3a-155">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="7fd3a-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7fd3a-156">VideoBitRateKB 設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="7fd3a-157">TotalReceiveVideoBitRateKB 設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="7fd3a-158">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7fd3a-159">EnableMultiviewJoin 設定為 False</span><span class="sxs-lookup"><span data-stu-id="7fd3a-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="7fd3a-160">對於所有其他員工，系統管理員會建立名為 StandardVideo 的會議原則。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="7fd3a-161">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="7fd3a-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="7fd3a-162">VideoBitRateKB 設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="7fd3a-163">TotalReceiveVideoBitRateKB 設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="7fd3a-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="7fd3a-164">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="7fd3a-165">EnableMultiviewJoin 設定為 True</span><span class="sxs-lookup"><span data-stu-id="7fd3a-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="7fd3a-166">管理員會將會議原則指派給使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7fd3a-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="7fd3a-167">ExecutiveVideo 會議原則指派給主管人員。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="7fd3a-168">BranchOfficeVideo 會議原則會指派給分支機搆中的所有員工。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="7fd3a-169">StandardVideo 會議原則會指派給所有其他員工。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="7fd3a-170">這些會議原則指派會導致下列使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="7fd3a-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="7fd3a-171">所有使用者支援函式庫視圖所組織的所有會議，但分支機搆中的員工無法體驗圖庫 View。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="7fd3a-172">對於任何雙方或多方會議，主管可以傳送 1920 x 1080 完整 HD 影片（如果其硬體和網路連結支援），而且可以接收其他參與者用戶端支援的 1920 x 1080 完整 HD 影片。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="7fd3a-173">非執行官員的員工體驗的解決方案低於雙方或多方會議中的主管，但仍然可獲得良好的解決方法。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="7fd3a-174">當 Lync 顯示預設的影片視窗大小時，位於分支辦公室的員工會在兩方通話中取得良好的視頻品質;不過，如果 Lync 視窗最大化為全螢幕，影片解析度將不會增加。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="7fd3a-175">對於多方會議，分支辦公室中的員工只會看到一個使用中影片。</span><span class="sxs-lookup"><span data-stu-id="7fd3a-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

