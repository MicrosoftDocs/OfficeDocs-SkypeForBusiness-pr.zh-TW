---
title: Lync Server 2013：行動效能計數器
description: Lync Server 2013：行動效能計數器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550529"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="e998c-103">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="e998c-103">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e998c-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e998c-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e998c-105">下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊網頁 API (UCWA) 和 Lync Server 2013 Mcx 行動性服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e998c-105">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="e998c-106">UCWA 資料表中的計數器類別名稱是 **LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="e998c-106">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="e998c-107">Mcx 行動性服務表格中的計數器類別名稱是 **LS： WEB Mobile Communication service**。</span><span class="sxs-lookup"><span data-stu-id="e998c-107">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="e998c-108">UCWA 的效能計數器</span><span class="sxs-lookup"><span data-stu-id="e998c-108">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e998c-109">計數器</span><span class="sxs-lookup"><span data-stu-id="e998c-109">Counter</span></span></th>
<th><span data-ttu-id="e998c-110">描述</span><span class="sxs-lookup"><span data-stu-id="e998c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e998c-111">使用中應用程式計數</span><span class="sxs-lookup"><span data-stu-id="e998c-111">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-112">目前的應用程式數目</span><span class="sxs-lookup"><span data-stu-id="e998c-112">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-113">使用中應用程式共用的形式計數</span><span class="sxs-lookup"><span data-stu-id="e998c-113">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-114">目前的應用程式共用形式數目</span><span class="sxs-lookup"><span data-stu-id="e998c-114">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-115">使用中音訊的模態計數</span><span class="sxs-lookup"><span data-stu-id="e998c-115">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-116">目前的音訊模態數目</span><span class="sxs-lookup"><span data-stu-id="e998c-116">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-117">主動資料共同作業模式計數</span><span class="sxs-lookup"><span data-stu-id="e998c-117">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-118">目前的資料共同作業數目</span><span class="sxs-lookup"><span data-stu-id="e998c-118">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-119">Active Directory 照片取得延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-119">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e998c-120">此計數器會顯示從 active directory 中取得相片的平均 (（毫秒）) </span><span class="sxs-lookup"><span data-stu-id="e998c-120">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-121">使用中的郵件模式計數</span><span class="sxs-lookup"><span data-stu-id="e998c-121">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-122">目前的郵件模態模式數目</span><span class="sxs-lookup"><span data-stu-id="e998c-122">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-123">使用中全景影片的模式計數</span><span class="sxs-lookup"><span data-stu-id="e998c-123">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-124">目前的全景影片形式數目</span><span class="sxs-lookup"><span data-stu-id="e998c-124">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-125">作用中擱置的取得計數</span><span class="sxs-lookup"><span data-stu-id="e998c-125">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-126">目前使用中擱置的取得數目;保留伺服器的長時間連接</span><span class="sxs-lookup"><span data-stu-id="e998c-126">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-127">主動會話計數</span><span class="sxs-lookup"><span data-stu-id="e998c-127">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-128">UCWA 中每個應用程式和總數所註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="e998c-128">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-129">作用中使用者實例計數</span><span class="sxs-lookup"><span data-stu-id="e998c-129">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-130">目前的使用者實例數目</span><span class="sxs-lookup"><span data-stu-id="e998c-130">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-131">不含應用程式的作用中使用者實例</span><span class="sxs-lookup"><span data-stu-id="e998c-131">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="e998c-132">目前沒有 application 的使用者實例數目</span><span class="sxs-lookup"><span data-stu-id="e998c-132">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-133">使用中影片的模態計數</span><span class="sxs-lookup"><span data-stu-id="e998c-133">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-134">目前影片的模態數目</span><span class="sxs-lookup"><span data-stu-id="e998c-134">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-135">每秒收到的應用程式建立要求</span><span class="sxs-lookup"><span data-stu-id="e998c-135">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-136">每秒收到應用程式建立要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-136">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-137">作為 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-137">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-138">作為 MCU 加入失敗的數目</span><span class="sxs-lookup"><span data-stu-id="e998c-138">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-139">AV MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-139">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-140">AV MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="e998c-140">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-141">平均應用程式啟動時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-141">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="e998c-142">應用程式的平均啟動時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e998c-142">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-143">會話的平均壽命 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-143">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="e998c-144">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e998c-144">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-145">資料 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-145">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-146">資料 MCU 加入失敗次數</span><span class="sxs-lookup"><span data-stu-id="e998c-146">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-147">Exchange 連絡人搜尋延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-147">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e998c-148">此計數器會顯示在 Exchange 中搜尋連絡人的平均 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-148">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-149">Exchange HD 相片取得延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="e998c-149">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="e998c-150">此計數器會顯示從 Exchange 取得相片的平均 (（毫秒）) </span><span class="sxs-lookup"><span data-stu-id="e998c-150">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-151">HTTP 4xx 回應數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-151">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-152">每秒以 HTTP 4xx 代碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-152">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-153">HTTP 5xx 回應數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-153">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-154">每秒以 HTTP 5xx 代碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-154">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-155">IM MCU 聯接失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-155">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-156">IM MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="e998c-156">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-157">Active Directory 照片取得失敗的數目</span><span class="sxs-lookup"><span data-stu-id="e998c-157">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-158">從 Active Directory 中取得相片的失敗總數</span><span class="sxs-lookup"><span data-stu-id="e998c-158">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-159">連絡人搜尋失敗次數</span><span class="sxs-lookup"><span data-stu-id="e998c-159">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-160">在 Exchange 中搜尋連絡人的失敗總數</span><span class="sxs-lookup"><span data-stu-id="e998c-160">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-161">反序列化失敗次數</span><span class="sxs-lookup"><span data-stu-id="e998c-161">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-162">反序列化失敗總數</span><span class="sxs-lookup"><span data-stu-id="e998c-162">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-163">HD 相片 Get 失敗次數</span><span class="sxs-lookup"><span data-stu-id="e998c-163">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-164">從 Exchange 取得 HD 相片的失敗總次數</span><span class="sxs-lookup"><span data-stu-id="e998c-164">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-165">每個應用程式的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="e998c-165">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="e998c-166">每個應用程式允許的最大訂閱要求數目</span><span class="sxs-lookup"><span data-stu-id="e998c-166">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-167">每個批次的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="e998c-167">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="e998c-168">每個批次允許的訂閱要求數目上限</span><span class="sxs-lookup"><span data-stu-id="e998c-168">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-169">目前狀態訂閱失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-169">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-170">訂閱目前狀態失敗的次數</span><span class="sxs-lookup"><span data-stu-id="e998c-170">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-171">註冊端點失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-171">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="e998c-172">註冊端點的失敗次數</span><span class="sxs-lookup"><span data-stu-id="e998c-172">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-173">接收的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-173">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-174">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-174">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-175">每秒成功的要求</span><span class="sxs-lookup"><span data-stu-id="e998c-175">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-176">每秒成功要求 (HTTP 2xx/3xx 回應碼的速率) </span><span class="sxs-lookup"><span data-stu-id="e998c-176">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-177">成功建立應用程式 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="e998c-177">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-178">每秒成功的應用程式建立要求速率</span><span class="sxs-lookup"><span data-stu-id="e998c-178">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-179">超時等候中的取得計數</span><span class="sxs-lookup"><span data-stu-id="e998c-179">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-180">超時的擱置取得數目</span><span class="sxs-lookup"><span data-stu-id="e998c-180">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-181">已接收的應用程式建立要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-181">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="e998c-182">啟動服務後收到的應用程式建立要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-182">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-183">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="e998c-183">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="e998c-184">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="e998c-184">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-185">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="e998c-185">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="e998c-186">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="e998c-186">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-187">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-187">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="e998c-188">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-188">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-189">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-189">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e998c-190">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-190">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-191">起始的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-191">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="e998c-192">啟動服務後所初始化的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-192">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-193">因空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-193">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="e998c-194">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-194">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-195">限制的應用程式總數</span><span class="sxs-lookup"><span data-stu-id="e998c-195">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="e998c-196">節流應用程式的數目</span><span class="sxs-lookup"><span data-stu-id="e998c-196">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="e998c-197">Mcx 行動性服務的效能計數器</span><span class="sxs-lookup"><span data-stu-id="e998c-197">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e998c-198">計數器</span><span class="sxs-lookup"><span data-stu-id="e998c-198">Counter</span></span></th>
<th><span data-ttu-id="e998c-199">描述</span><span class="sxs-lookup"><span data-stu-id="e998c-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e998c-200">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e998c-200">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="e998c-201">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="e998c-201">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-202">目前的推播通知訂閱</span><span class="sxs-lookup"><span data-stu-id="e998c-202">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="e998c-203">推播通知訂閱的目前數目。</span><span class="sxs-lookup"><span data-stu-id="e998c-203">The current number of push notification subscriptions.</span></span> <span data-ttu-id="e998c-204">這個數目會與目前作用中的會話計數搭配使用，代表為 Windows Mobile 或 iPhone 裝置註冊的目前作用中會話的子集。</span><span class="sxs-lookup"><span data-stu-id="e998c-204">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-205">目前使用中的網路超時輪詢計數</span><span class="sxs-lookup"><span data-stu-id="e998c-205">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-206">超時的網路輪詢數目</span><span class="sxs-lookup"><span data-stu-id="e998c-206">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-207">目前使用中的輪詢計數</span><span class="sxs-lookup"><span data-stu-id="e998c-207">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-208">目前使用中輪詢的數目 (長期保留與伺服器的連線) </span><span class="sxs-lookup"><span data-stu-id="e998c-208">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-209">目前使用中的會話計數</span><span class="sxs-lookup"><span data-stu-id="e998c-209">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-210">目前在行動服務中註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="e998c-210">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-211">目前使用中的會話計數與使用中狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="e998c-211">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="e998c-212">目前使用中狀態訂閱的目前活動會話數目</span><span class="sxs-lookup"><span data-stu-id="e998c-212">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-213">推播通知要求失敗/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-213">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-214">每秒失敗推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-214">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-215">每秒成功的推入通知要求</span><span class="sxs-lookup"><span data-stu-id="e998c-215">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-216">每秒成功推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-216">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-217">限制的推播通知要求數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-217">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-218">每秒節流推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-218">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-219">推播通知 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="e998c-219">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-220">每秒傳送推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-220">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-221">每秒失敗的要求</span><span class="sxs-lookup"><span data-stu-id="e998c-221">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-222">每秒失敗要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-222">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-223">接收的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-223">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-224">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-224">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-225">拒絕的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="e998c-225">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-226">每秒拒絕要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-226">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-227">每秒成功的要求</span><span class="sxs-lookup"><span data-stu-id="e998c-227">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-228">每秒成功要求的速率</span><span class="sxs-lookup"><span data-stu-id="e998c-228">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-229">已成功啟動會話 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="e998c-229">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="e998c-230">每秒成功取得位置要求的速率。</span><span class="sxs-lookup"><span data-stu-id="e998c-230">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="e998c-231">啟動會話的要求會消耗伺服器上的大部分 CPU。</span><span class="sxs-lookup"><span data-stu-id="e998c-231">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="e998c-232">支援的負載峰值為 12/秒。</span><span class="sxs-lookup"><span data-stu-id="e998c-232">Peak supported load is 12/second.</span></span> <span data-ttu-id="e998c-233">可持續性取決於伺服器上的其他負載。</span><span class="sxs-lookup"><span data-stu-id="e998c-233">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="e998c-234">[啟動會話] 通常表示登入的使用者已長時間簽入的使用者。</span><span class="sxs-lookup"><span data-stu-id="e998c-234">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-235">拒絕的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-235">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e998c-236">已謝絕的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-236">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-237">失敗的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-237">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e998c-238">失敗的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-238">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-239">失敗的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-239">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e998c-240">失敗的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-240">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-241">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-241">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="e998c-242">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-242">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-243">推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-243">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="e998c-244">推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-244">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-245">推播通知要求總數失敗</span><span class="sxs-lookup"><span data-stu-id="e998c-245">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="e998c-246">失敗的推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-246">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-247">已成功的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-247">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e998c-248">成功的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-248">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-249">限制的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-249">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="e998c-250">已節流之推播通知要求的總數</span><span class="sxs-lookup"><span data-stu-id="e998c-250">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-251">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-251">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="e998c-252">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-252">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-253">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-253">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="e998c-254">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-254">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-255">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-255">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="e998c-256">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-256">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-257">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="e998c-257">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="e998c-258">已成功完成行動服務的總要求數</span><span class="sxs-lookup"><span data-stu-id="e998c-258">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-259">會話起始計數總數</span><span class="sxs-lookup"><span data-stu-id="e998c-259">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="e998c-260">啟動行動服務後所啟動的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-260">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-261">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-261">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="e998c-262">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-262">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e998c-263">成功輸入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-263">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e998c-264">輸入語音通話的成功總數</span><span class="sxs-lookup"><span data-stu-id="e998c-264">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e998c-265">成功的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="e998c-265">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="e998c-266">已成功撥出語音通話的總數</span><span class="sxs-lookup"><span data-stu-id="e998c-266">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

