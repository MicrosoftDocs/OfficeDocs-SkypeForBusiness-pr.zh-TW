---
title: Lync Server 2013：行動效能計數器
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
ms.openlocfilehash: 37e36b4492814043317fcafb2612a28c9f4d7b91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513600"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="beaff-102">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="beaff-102">Mobility performance counters in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beaff-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="beaff-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="beaff-104">下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊網頁 API (UCWA) 和 Lync Server 2013 Mcx 行動性服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="beaff-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="beaff-105">UCWA 資料表中的計數器類別名稱是 **LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="beaff-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="beaff-106">Mcx 行動性服務表格中的計數器類別名稱是 **LS： WEB Mobile Communication service**。</span><span class="sxs-lookup"><span data-stu-id="beaff-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="beaff-107">UCWA 的效能計數器</span><span class="sxs-lookup"><span data-stu-id="beaff-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaff-108">計數器</span><span class="sxs-lookup"><span data-stu-id="beaff-108">Counter</span></span></th>
<th><span data-ttu-id="beaff-109">描述</span><span class="sxs-lookup"><span data-stu-id="beaff-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaff-110">使用中應用程式計數</span><span class="sxs-lookup"><span data-stu-id="beaff-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-111">目前的應用程式數目</span><span class="sxs-lookup"><span data-stu-id="beaff-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-112">使用中應用程式共用的形式計數</span><span class="sxs-lookup"><span data-stu-id="beaff-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-113">目前的應用程式共用形式數目</span><span class="sxs-lookup"><span data-stu-id="beaff-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-114">使用中音訊的模態計數</span><span class="sxs-lookup"><span data-stu-id="beaff-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-115">目前的音訊模態數目</span><span class="sxs-lookup"><span data-stu-id="beaff-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-116">主動資料共同作業模式計數</span><span class="sxs-lookup"><span data-stu-id="beaff-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-117">目前的資料共同作業數目</span><span class="sxs-lookup"><span data-stu-id="beaff-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-118">Active Directory 照片取得延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="beaff-119">此計數器會顯示從 active directory 中取得相片的平均 (（毫秒）) </span><span class="sxs-lookup"><span data-stu-id="beaff-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-120">使用中的郵件模式計數</span><span class="sxs-lookup"><span data-stu-id="beaff-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-121">目前的郵件模態模式數目</span><span class="sxs-lookup"><span data-stu-id="beaff-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-122">使用中全景影片的模式計數</span><span class="sxs-lookup"><span data-stu-id="beaff-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-123">目前的全景影片形式數目</span><span class="sxs-lookup"><span data-stu-id="beaff-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-124">作用中擱置的取得計數</span><span class="sxs-lookup"><span data-stu-id="beaff-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-125">目前使用中擱置的取得數目;保留伺服器的長時間連接</span><span class="sxs-lookup"><span data-stu-id="beaff-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-126">主動會話計數</span><span class="sxs-lookup"><span data-stu-id="beaff-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-127">UCWA 中每個應用程式和總數所註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="beaff-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-128">作用中使用者實例計數</span><span class="sxs-lookup"><span data-stu-id="beaff-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-129">目前的使用者實例數目</span><span class="sxs-lookup"><span data-stu-id="beaff-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-130">不含應用程式的作用中使用者實例</span><span class="sxs-lookup"><span data-stu-id="beaff-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="beaff-131">目前沒有 application 的使用者實例數目</span><span class="sxs-lookup"><span data-stu-id="beaff-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-132">使用中影片的模態計數</span><span class="sxs-lookup"><span data-stu-id="beaff-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-133">目前影片的模態數目</span><span class="sxs-lookup"><span data-stu-id="beaff-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-134">每秒收到的應用程式建立要求</span><span class="sxs-lookup"><span data-stu-id="beaff-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-135">每秒收到應用程式建立要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-136">作為 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-137">作為 MCU 加入失敗的數目</span><span class="sxs-lookup"><span data-stu-id="beaff-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-138">AV MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-139">AV MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="beaff-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-140">平均應用程式啟動時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="beaff-141">應用程式的平均啟動時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="beaff-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-142">會話的平均壽命 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="beaff-143">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="beaff-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-144">資料 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-145">資料 MCU 加入失敗次數</span><span class="sxs-lookup"><span data-stu-id="beaff-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-146">Exchange 連絡人搜尋延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="beaff-147">此計數器會顯示在 Exchange 中搜尋連絡人的平均 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-148">Exchange HD 相片取得延遲 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="beaff-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="beaff-149">此計數器會顯示從 Exchange 取得相片的平均 (（毫秒）) </span><span class="sxs-lookup"><span data-stu-id="beaff-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-150">HTTP 4xx 回應數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-151">每秒以 HTTP 4xx 代碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-152">HTTP 5xx 回應數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-153">每秒以 HTTP 5xx 代碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-154">IM MCU 聯接失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-155">IM MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="beaff-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-156">Active Directory 照片取得失敗的數目</span><span class="sxs-lookup"><span data-stu-id="beaff-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-157">從 Active Directory 中取得相片的失敗總數</span><span class="sxs-lookup"><span data-stu-id="beaff-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-158">連絡人搜尋失敗次數</span><span class="sxs-lookup"><span data-stu-id="beaff-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-159">在 Exchange 中搜尋連絡人的失敗總數</span><span class="sxs-lookup"><span data-stu-id="beaff-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-160">反序列化失敗次數</span><span class="sxs-lookup"><span data-stu-id="beaff-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-161">反序列化失敗總數</span><span class="sxs-lookup"><span data-stu-id="beaff-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-162">HD 相片 Get 失敗次數</span><span class="sxs-lookup"><span data-stu-id="beaff-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-163">從 Exchange 取得 HD 相片的失敗總次數</span><span class="sxs-lookup"><span data-stu-id="beaff-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-164">每個應用程式的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="beaff-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="beaff-165">每個應用程式允許的最大訂閱要求數目</span><span class="sxs-lookup"><span data-stu-id="beaff-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-166">每個批次的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="beaff-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="beaff-167">每個批次允許的訂閱要求數目上限</span><span class="sxs-lookup"><span data-stu-id="beaff-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-168">目前狀態訂閱失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-169">訂閱目前狀態失敗的次數</span><span class="sxs-lookup"><span data-stu-id="beaff-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-170">註冊端點失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="beaff-171">註冊端點的失敗次數</span><span class="sxs-lookup"><span data-stu-id="beaff-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-172">接收的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-173">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-174">每秒成功的要求</span><span class="sxs-lookup"><span data-stu-id="beaff-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-175">每秒成功要求 (HTTP 2xx/3xx 回應碼的速率) </span><span class="sxs-lookup"><span data-stu-id="beaff-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-176">成功建立應用程式 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="beaff-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-177">每秒成功的應用程式建立要求速率</span><span class="sxs-lookup"><span data-stu-id="beaff-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-178">超時等候中的取得計數</span><span class="sxs-lookup"><span data-stu-id="beaff-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-179">超時的擱置取得數目</span><span class="sxs-lookup"><span data-stu-id="beaff-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-180">已接收的應用程式建立要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="beaff-181">啟動服務後收到的應用程式建立要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-182">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="beaff-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="beaff-183">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="beaff-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-184">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="beaff-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="beaff-185">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="beaff-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-186">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="beaff-187">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-188">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="beaff-189">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-190">起始的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="beaff-191">啟動服務後所初始化的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-192">因空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="beaff-193">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-194">限制的應用程式總數</span><span class="sxs-lookup"><span data-stu-id="beaff-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="beaff-195">節流應用程式的數目</span><span class="sxs-lookup"><span data-stu-id="beaff-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="beaff-196">Mcx 行動性服務的效能計數器</span><span class="sxs-lookup"><span data-stu-id="beaff-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="beaff-197">計數器</span><span class="sxs-lookup"><span data-stu-id="beaff-197">Counter</span></span></th>
<th><span data-ttu-id="beaff-198">描述</span><span class="sxs-lookup"><span data-stu-id="beaff-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="beaff-199">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="beaff-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="beaff-200">會話的平均生命週期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="beaff-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-201">目前的推播通知訂閱</span><span class="sxs-lookup"><span data-stu-id="beaff-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="beaff-202">推播通知訂閱的目前數目。</span><span class="sxs-lookup"><span data-stu-id="beaff-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="beaff-203">這個數目會與目前作用中的會話計數搭配使用，代表為 Windows Mobile 或 iPhone 裝置註冊的目前作用中會話的子集。</span><span class="sxs-lookup"><span data-stu-id="beaff-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-204">目前使用中的網路超時輪詢計數</span><span class="sxs-lookup"><span data-stu-id="beaff-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-205">超時的網路輪詢數目</span><span class="sxs-lookup"><span data-stu-id="beaff-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-206">目前使用中的輪詢計數</span><span class="sxs-lookup"><span data-stu-id="beaff-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-207">目前使用中輪詢的數目 (長期保留與伺服器的連線) </span><span class="sxs-lookup"><span data-stu-id="beaff-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-208">目前使用中的會話計數</span><span class="sxs-lookup"><span data-stu-id="beaff-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-209">目前在行動服務中註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="beaff-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-210">目前使用中的會話計數與使用中狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="beaff-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="beaff-211">目前使用中狀態訂閱的目前活動會話數目</span><span class="sxs-lookup"><span data-stu-id="beaff-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-212">推播通知要求失敗/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-213">每秒失敗推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-214">每秒成功的推入通知要求</span><span class="sxs-lookup"><span data-stu-id="beaff-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-215">每秒成功推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-216">限制的推播通知要求數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-217">每秒節流推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-218">推播通知 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="beaff-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-219">每秒傳送推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-220">每秒失敗的要求</span><span class="sxs-lookup"><span data-stu-id="beaff-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-221">每秒失敗要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-222">接收的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-223">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-224">拒絕的要求數/秒</span><span class="sxs-lookup"><span data-stu-id="beaff-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-225">每秒拒絕要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-226">每秒成功的要求</span><span class="sxs-lookup"><span data-stu-id="beaff-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-227">每秒成功要求的速率</span><span class="sxs-lookup"><span data-stu-id="beaff-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-228">已成功啟動會話 Requests/Second</span><span class="sxs-lookup"><span data-stu-id="beaff-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="beaff-229">每秒成功取得位置要求的速率。</span><span class="sxs-lookup"><span data-stu-id="beaff-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="beaff-230">啟動會話的要求會消耗伺服器上的大部分 CPU。</span><span class="sxs-lookup"><span data-stu-id="beaff-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="beaff-231">支援的負載峰值為 12/秒。</span><span class="sxs-lookup"><span data-stu-id="beaff-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="beaff-232">可持續性取決於伺服器上的其他負載。</span><span class="sxs-lookup"><span data-stu-id="beaff-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="beaff-233">[啟動會話] 通常表示登入的使用者已長時間簽入的使用者。</span><span class="sxs-lookup"><span data-stu-id="beaff-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-234">拒絕的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="beaff-235">已謝絕的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-236">失敗的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="beaff-237">失敗的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-238">失敗的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="beaff-239">失敗的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-240">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="beaff-241">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-242">推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="beaff-243">推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-244">推播通知要求總數失敗</span><span class="sxs-lookup"><span data-stu-id="beaff-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="beaff-245">失敗的推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-246">已成功的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="beaff-247">成功的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-248">限制的推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="beaff-249">已節流之推播通知要求的總數</span><span class="sxs-lookup"><span data-stu-id="beaff-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-250">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="beaff-251">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-252">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="beaff-253">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-254">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="beaff-255">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-256">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="beaff-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="beaff-257">已成功完成行動服務的總要求數</span><span class="sxs-lookup"><span data-stu-id="beaff-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-258">會話起始計數總數</span><span class="sxs-lookup"><span data-stu-id="beaff-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="beaff-259">啟動行動服務後所啟動的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-260">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="beaff-261">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="beaff-262">成功輸入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="beaff-263">輸入語音通話的成功總數</span><span class="sxs-lookup"><span data-stu-id="beaff-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="beaff-264">成功的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="beaff-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="beaff-265">已成功撥出語音通話的總數</span><span class="sxs-lookup"><span data-stu-id="beaff-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

