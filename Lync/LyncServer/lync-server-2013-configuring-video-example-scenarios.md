---
title: Lync Server 2013： 設定視訊範例案例
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
ms.openlocfilehash: 128703a39563124f6abfc4ae44143d274fd3a7c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="e8c07-102">Lync Server 2013 設定視訊範例案例</span><span class="sxs-lookup"><span data-stu-id="e8c07-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8c07-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="e8c07-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e8c07-104">Lync 2013 新增視訊功能以支援 1920 x 1080 全彩高畫質 (HD) 視訊與圖庫檢視視訊。</span><span class="sxs-lookup"><span data-stu-id="e8c07-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="e8c07-105">根據客戶資料的度量單位顯示一般的視訊頻寬增加僅稍微相較於 Lync 2010，但最大視訊資料流頻寬已經增加由於完整 HD 支援 （如需詳細資訊，請參閱中[的 Lync Server 2013 中的媒體流量網路頻寬需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)的 「 媒體流量網路使用率 」 一節）。</span><span class="sxs-lookup"><span data-stu-id="e8c07-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="e8c07-106">因此，系統管理員可能會想要限制特定使用者 （例如中具有較少的網路容量的分公司的使用者） 的視訊頻寬及協助確保最佳視訊品質的其他使用者 （例如主管）。</span><span class="sxs-lookup"><span data-stu-id="e8c07-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="e8c07-107">下表提供建議設定的清單設定不同的網路容量的影片。</span><span class="sxs-lookup"><span data-stu-id="e8c07-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="e8c07-108">這些設定會傳送及接收較高 （請參閱右方的欄） 的解析度的視訊限制某些使用者的案例。</span><span class="sxs-lookup"><span data-stu-id="e8c07-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="e8c07-109">最小的設定會導致無法使用的圖庫影片，由於低的最大值會收到的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="e8c07-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="e8c07-110">建議的視訊設定</span><span class="sxs-lookup"><span data-stu-id="e8c07-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="e8c07-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="e8c07-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="e8c07-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="e8c07-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="e8c07-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="e8c07-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="e8c07-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="e8c07-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="e8c07-115">預期的品質良好視訊解析度的視訊</span><span class="sxs-lookup"><span data-stu-id="e8c07-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8c07-116">最佳</span><span class="sxs-lookup"><span data-stu-id="e8c07-116">Best</span></span></p></td>
<td><p><span data-ttu-id="e8c07-117">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-117">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-118">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-118">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-119">8000</span><span class="sxs-lookup"><span data-stu-id="e8c07-119">8000</span></span></p></td>
<td><p><span data-ttu-id="e8c07-120">8000</span><span class="sxs-lookup"><span data-stu-id="e8c07-120">8000</span></span></p></td>
<td><p><span data-ttu-id="e8c07-121">若要對等： 最 1920 x 1080 的視訊解析度</span><span class="sxs-lookup"><span data-stu-id="e8c07-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="e8c07-122">圖庫檢視： 最多兩個 1920 x 1080 的視訊或多個較小解析度的視訊</span><span class="sxs-lookup"><span data-stu-id="e8c07-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8c07-123">良好</span><span class="sxs-lookup"><span data-stu-id="e8c07-123">Good</span></span></p></td>
<td><p><span data-ttu-id="e8c07-124">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-124">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-125">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-125">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-126">2500</span><span class="sxs-lookup"><span data-stu-id="e8c07-126">2500</span></span></p></td>
<td><p><span data-ttu-id="e8c07-127">2500</span><span class="sxs-lookup"><span data-stu-id="e8c07-127">2500</span></span></p></td>
<td><p><span data-ttu-id="e8c07-128">若要對等： 最高 1280 x 720 的視訊解析度</span><span class="sxs-lookup"><span data-stu-id="e8c07-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="e8c07-129">圖庫檢視： 最多五個 640 x 360 解析度的視訊</span><span class="sxs-lookup"><span data-stu-id="e8c07-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8c07-130">中</span><span class="sxs-lookup"><span data-stu-id="e8c07-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="e8c07-131">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-131">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-132">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-132">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-133">1000</span><span class="sxs-lookup"><span data-stu-id="e8c07-133">1000</span></span></p></td>
<td><p><span data-ttu-id="e8c07-134">1000</span><span class="sxs-lookup"><span data-stu-id="e8c07-134">1000</span></span></p></td>
<td><p><span data-ttu-id="e8c07-135">若要對等： 最高 960 x 540 的視訊解析度</span><span class="sxs-lookup"><span data-stu-id="e8c07-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="e8c07-136">圖庫檢視： 最多五個 424 x 240 解析度的視訊</span><span class="sxs-lookup"><span data-stu-id="e8c07-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8c07-137">最小值</span><span class="sxs-lookup"><span data-stu-id="e8c07-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="e8c07-138">True</span><span class="sxs-lookup"><span data-stu-id="e8c07-138">True</span></span></p></td>
<td><p><span data-ttu-id="e8c07-139">False</span><span class="sxs-lookup"><span data-stu-id="e8c07-139">False</span></span></p></td>
<td><p><span data-ttu-id="e8c07-140">350</span><span class="sxs-lookup"><span data-stu-id="e8c07-140">350</span></span></p></td>
<td><p><span data-ttu-id="e8c07-141">350</span><span class="sxs-lookup"><span data-stu-id="e8c07-141">350</span></span></p></td>
<td><p><span data-ttu-id="e8c07-142">若要對等： 最高 424 x 240 的視訊解析度</span><span class="sxs-lookup"><span data-stu-id="e8c07-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="e8c07-143">圖庫檢視： 無法使用</span><span class="sxs-lookup"><span data-stu-id="e8c07-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e8c07-144">您可以使用上表中的資訊來部署新的 HD 視訊與圖庫檢視 」 視訊會議功能，部分使用者在您組織中，同時允許其他人的不同的視訊解析度。</span><span class="sxs-lookup"><span data-stu-id="e8c07-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="e8c07-145">在下列範例中，系統管理員可用的最高視訊品質新視訊功能回復才能主管。</span><span class="sxs-lookup"><span data-stu-id="e8c07-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="e8c07-146">低網路容量遠端分公司中的員工，就會部署只從上表的最小設定。</span><span class="sxs-lookup"><span data-stu-id="e8c07-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="e8c07-147">其他所有員工，就會部署上述表格中的 「 良好 」 設定。</span><span class="sxs-lookup"><span data-stu-id="e8c07-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="e8c07-148">若要推行至高階主管的新功能，系統管理員會建立名為 ExecutiveVideo 會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8c07-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="e8c07-149">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="e8c07-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e8c07-150">VideoBitRateKB 設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="e8c07-151">TotalReceiveVideoBitRateKB 設定為 8000 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="e8c07-152">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="e8c07-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e8c07-153">EnableMultiviewJoin 設定為 True</span><span class="sxs-lookup"><span data-stu-id="e8c07-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="e8c07-154">在分公司員工，系統管理員會建立名為 BranchOfficeVideo 會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8c07-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="e8c07-155">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="e8c07-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e8c07-156">VideoBitRateKB 設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="e8c07-157">TotalReceiveVideoBitRateKB 設定為 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="e8c07-158">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="e8c07-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e8c07-159">EnableMultiviewJoin 設定為 False</span><span class="sxs-lookup"><span data-stu-id="e8c07-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="e8c07-160">其他所有員工，系統管理員會建立名為 StandardVideo 會議原則。</span><span class="sxs-lookup"><span data-stu-id="e8c07-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="e8c07-161">此會議原則具有下列設定：</span><span class="sxs-lookup"><span data-stu-id="e8c07-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="e8c07-162">VideoBitRateKB 設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="e8c07-163">TotalReceiveVideoBitRateKB 設定為 2500 Kbps</span><span class="sxs-lookup"><span data-stu-id="e8c07-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="e8c07-164">AllowMultiview 設定為 True</span><span class="sxs-lookup"><span data-stu-id="e8c07-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="e8c07-165">EnableMultiviewJoin 設定為 True</span><span class="sxs-lookup"><span data-stu-id="e8c07-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="e8c07-166">系統管理員會將會議原則給使用者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8c07-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="e8c07-167">將 ExecutiveVideo 會議原則指派給高階主管。</span><span class="sxs-lookup"><span data-stu-id="e8c07-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="e8c07-168">將 BranchOfficeVideo 會議原則指派給分公司中的所有員工。</span><span class="sxs-lookup"><span data-stu-id="e8c07-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="e8c07-169">將 StandardVideo 會議原則指派給所有其他員工。</span><span class="sxs-lookup"><span data-stu-id="e8c07-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="e8c07-170">這些會議原則指派產生下列使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="e8c07-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="e8c07-171">任何使用者召集的所有會議都支援圖庫檢視，但分公司員工無法體驗圖庫檢視。</span><span class="sxs-lookup"><span data-stu-id="e8c07-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="e8c07-172">針對任何雙方或多方會議，主管可以傳送 1920 x 1080 全彩 HD 視訊，如果其硬體與網路連結支援，而且可接收 1920 x 1080 全 HD 視訊其中其他參與者用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="e8c07-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="e8c07-173">非高階主管的員工體驗的解析度低於高階主管在雙方或多方會議，但仍屬良好解析度。</span><span class="sxs-lookup"><span data-stu-id="e8c07-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="e8c07-174">在分公司員工會良好視訊品質在雙方通話時取得 Lync 顯示預設的視訊視窗大小;不過，如果 Lync 視窗最大化至全螢幕，將不會增加的視訊解析度。</span><span class="sxs-lookup"><span data-stu-id="e8c07-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="e8c07-175">多方會議，在分公司員工將會看到只能有一個作用中的影片。</span><span class="sxs-lookup"><span data-stu-id="e8c07-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

