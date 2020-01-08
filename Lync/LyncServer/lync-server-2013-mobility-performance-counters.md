---
title: Lync Server 2013：行動性效能計數器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="095ea-102">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="095ea-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="095ea-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="095ea-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="095ea-104">下表列出效能計數器的名稱和描述，您可以用來監視執行整合通訊 Web API （UCWA）和 Lync Server 2013 Mcx 行動服務的伺服器。</span><span class="sxs-lookup"><span data-stu-id="095ea-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="095ea-105">UCWA 資料表中計數器的類別名稱是**LS： WEB – UCWA**。</span><span class="sxs-lookup"><span data-stu-id="095ea-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="095ea-106">Mcx 行動服務資料表中計數器的類別名稱是**LS： WEB Mobile 通訊服務**。</span><span class="sxs-lookup"><span data-stu-id="095ea-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="095ea-107">UCWA 的效能計數器</span><span class="sxs-lookup"><span data-stu-id="095ea-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="095ea-108">反</span><span class="sxs-lookup"><span data-stu-id="095ea-108">Counter</span></span></th>
<th><span data-ttu-id="095ea-109">描述</span><span class="sxs-lookup"><span data-stu-id="095ea-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="095ea-110">作用中的應用程式計數</span><span class="sxs-lookup"><span data-stu-id="095ea-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-111">目前的應用程式數</span><span class="sxs-lookup"><span data-stu-id="095ea-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-112">使用中的應用程式共用模態計數</span><span class="sxs-lookup"><span data-stu-id="095ea-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-113">應用程式共用模態的目前數量</span><span class="sxs-lookup"><span data-stu-id="095ea-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-114">使用中的音訊模態計數</span><span class="sxs-lookup"><span data-stu-id="095ea-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-115">目前的音訊模態數量</span><span class="sxs-lookup"><span data-stu-id="095ea-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-116">活動資料共同作業計數</span><span class="sxs-lookup"><span data-stu-id="095ea-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-117">目前的資料共同作業數</span><span class="sxs-lookup"><span data-stu-id="095ea-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-118">Active Directory 相片取得延遲（毫秒）</span><span class="sxs-lookup"><span data-stu-id="095ea-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="095ea-119">這個計數器顯示從 active directory 中檢索相片的平均時間（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-120">使用中的訊息模態計數</span><span class="sxs-lookup"><span data-stu-id="095ea-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-121">目前的訊息模態數量</span><span class="sxs-lookup"><span data-stu-id="095ea-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-122">使用中全景視頻的狀態計數</span><span class="sxs-lookup"><span data-stu-id="095ea-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-123">目前的全景視頻模態數量</span><span class="sxs-lookup"><span data-stu-id="095ea-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-124">作用中未決取得計數</span><span class="sxs-lookup"><span data-stu-id="095ea-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-125">目前處於作用中未決的取得次數;在伺服器上保留較長的連線連接</span><span class="sxs-lookup"><span data-stu-id="095ea-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-126">活動會話計數</span><span class="sxs-lookup"><span data-stu-id="095ea-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-127">每個應用程式在 UCWA 中註冊的端點數目及總計</span><span class="sxs-lookup"><span data-stu-id="095ea-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-128">作用中使用者實例計數</span><span class="sxs-lookup"><span data-stu-id="095ea-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-129">目前的使用者實例數</span><span class="sxs-lookup"><span data-stu-id="095ea-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-130">不含應用程式的作用中使用者實例</span><span class="sxs-lookup"><span data-stu-id="095ea-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="095ea-131">目前不含應用程式的使用者實例數</span><span class="sxs-lookup"><span data-stu-id="095ea-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-132">使用中的視頻模態統計</span><span class="sxs-lookup"><span data-stu-id="095ea-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-133">目前的視頻模態數量</span><span class="sxs-lookup"><span data-stu-id="095ea-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-134">收到的應用程式建立要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-135">每秒收到應用程式建立要求的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-136">作為 MCU 連接失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-137">MCU 連接失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-138">AV MCU 聯接失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-139">AV MCU 連接失敗次數</span><span class="sxs-lookup"><span data-stu-id="095ea-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-140">應用程式的平均啟動時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="095ea-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="095ea-141">應用程式的平均啟動時間（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-142">會話的平均存留期（毫秒）</span><span class="sxs-lookup"><span data-stu-id="095ea-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="095ea-143">會話的平均存留期（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-144">資料 MCU 連接失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-145">資料 MCU 連接失敗次數</span><span class="sxs-lookup"><span data-stu-id="095ea-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-146">Exchange 連絡人搜尋延遲時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="095ea-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="095ea-147">這個計數器顯示在 Exchange 中搜尋連絡人的平均時間（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-148">Exchange HD 相片取得延遲（毫秒）</span><span class="sxs-lookup"><span data-stu-id="095ea-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="095ea-149">這個計數器顯示從 Exchange 中檢索相片的平均時間（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-150">HTTP 4xx 回應/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-151">每秒回應與 HTTP 4xx 代碼的回應速率</span><span class="sxs-lookup"><span data-stu-id="095ea-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-152">HTTP 5xx 回應/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-153">每秒回應與 HTTP 5xx 代碼的回應速率</span><span class="sxs-lookup"><span data-stu-id="095ea-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-154">IM MCU 連接失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-155">IM MCU 連接失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-156">Active Directory 相片取得失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-157">從 Active Directory 中檢索相片的失敗總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-158">連絡人搜尋失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-159">在 Exchange 中搜尋連絡人的失敗總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-160">反序列化失敗次數</span><span class="sxs-lookup"><span data-stu-id="095ea-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-161">反序列化失敗的總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-162">HD 相片取得失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-163">從 Exchange 中取得 HD 相片的失敗總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-164">針對每個應用程式的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="095ea-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="095ea-165">每個應用程式允許的訂閱要求數目上限</span><span class="sxs-lookup"><span data-stu-id="095ea-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-166">針對每個批次的最大訂閱數</span><span class="sxs-lookup"><span data-stu-id="095ea-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="095ea-167">每個批次允許的訂閱要求數目上限</span><span class="sxs-lookup"><span data-stu-id="095ea-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-168">目前狀態訂閱失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-169">訂閱目前狀態失敗的次數</span><span class="sxs-lookup"><span data-stu-id="095ea-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-170">註冊端點失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="095ea-171">要註冊端點的失敗次數</span><span class="sxs-lookup"><span data-stu-id="095ea-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-172">收到的要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-173">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-174">成功的要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-175">每秒成功要求的速度（HTTP 2xx/3xx 回應碼）</span><span class="sxs-lookup"><span data-stu-id="095ea-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-176">已成功建立應用程式要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-177">成功應用程式建立要求的每秒匯率</span><span class="sxs-lookup"><span data-stu-id="095ea-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-178">已超時擱置中的 [取得計數]</span><span class="sxs-lookup"><span data-stu-id="095ea-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-179">超時的未決取得數</span><span class="sxs-lookup"><span data-stu-id="095ea-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-180">收到的應用程式建立要求總計</span><span class="sxs-lookup"><span data-stu-id="095ea-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="095ea-181">在服務啟動後收到的應用程式建立要求總數量</span><span class="sxs-lookup"><span data-stu-id="095ea-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-182">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="095ea-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="095ea-183">HTTP 4xx 回應總數目</span><span class="sxs-lookup"><span data-stu-id="095ea-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-184">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="095ea-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="095ea-185">HTTP 5xx 回應總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-186">在命令通道上接收到的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="095ea-187">在命令通道上接收到的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-188">成功總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="095ea-189">成功的要求總數量</span><span class="sxs-lookup"><span data-stu-id="095ea-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-190">啟動的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="095ea-191">啟動服務之後所啟動的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-192">因空閒超時而終止的總會話數</span><span class="sxs-lookup"><span data-stu-id="095ea-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="095ea-193">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-194">已限制的應用程式總計</span><span class="sxs-lookup"><span data-stu-id="095ea-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="095ea-195">受限制的應用程式數目</span><span class="sxs-lookup"><span data-stu-id="095ea-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="095ea-196">Mcx 行動服務的效能計數器</span><span class="sxs-lookup"><span data-stu-id="095ea-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="095ea-197">反</span><span class="sxs-lookup"><span data-stu-id="095ea-197">Counter</span></span></th>
<th><span data-ttu-id="095ea-198">描述</span><span class="sxs-lookup"><span data-stu-id="095ea-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="095ea-199">會話的平均存留期（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="095ea-200">會話的平均存留期（以毫秒為單位）</span><span class="sxs-lookup"><span data-stu-id="095ea-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-201">目前的推播通知訂閱</span><span class="sxs-lookup"><span data-stu-id="095ea-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="095ea-202">推播通知訂閱的目前數目。</span><span class="sxs-lookup"><span data-stu-id="095ea-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="095ea-203">這個數位與目前的活動會話計數，代表已針對 Windows Mobile 或 iPhone 裝置註冊的目前活動會話子集。</span><span class="sxs-lookup"><span data-stu-id="095ea-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-204">目前使用中的網路超時輪詢計數</span><span class="sxs-lookup"><span data-stu-id="095ea-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-205">超時的網路輪詢數</span><span class="sxs-lookup"><span data-stu-id="095ea-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-206">目前使用中的輪詢計數</span><span class="sxs-lookup"><span data-stu-id="095ea-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-207">目前使用中的輪詢數（與伺服器的長時間連接）</span><span class="sxs-lookup"><span data-stu-id="095ea-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-208">目前的活動會話計數</span><span class="sxs-lookup"><span data-stu-id="095ea-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-209">行動服務中的目前已註冊端點數目</span><span class="sxs-lookup"><span data-stu-id="095ea-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-210">目前處於作用中狀態訂閱的目前活動會話計數</span><span class="sxs-lookup"><span data-stu-id="095ea-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="095ea-211">目前處於作用中狀態訂閱的目前活動會話數</span><span class="sxs-lookup"><span data-stu-id="095ea-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-212">失敗/秒的推播通知要求</span><span class="sxs-lookup"><span data-stu-id="095ea-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-213">每秒失敗推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-214">成功/秒的推播通知要求</span><span class="sxs-lookup"><span data-stu-id="095ea-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-215">每秒成功推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-216">每秒限制的推播通知要求</span><span class="sxs-lookup"><span data-stu-id="095ea-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-217">每秒限制推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-218">推播通知要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-219">每秒傳送推播通知的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-220">失敗/秒的要求</span><span class="sxs-lookup"><span data-stu-id="095ea-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-221">每秒失敗要求的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-222">收到的要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-223">每秒收到要求的速率</span><span class="sxs-lookup"><span data-stu-id="095ea-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-224">拒絕的要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-225">拒絕的要求每秒的工資率</span><span class="sxs-lookup"><span data-stu-id="095ea-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-226">成功的要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-227">成功要求的每秒匯率</span><span class="sxs-lookup"><span data-stu-id="095ea-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-228">已成功啟動會話要求/秒</span><span class="sxs-lookup"><span data-stu-id="095ea-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="095ea-229">成功取得位置要求的每秒利率。</span><span class="sxs-lookup"><span data-stu-id="095ea-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="095ea-230">啟動會話的要求會佔用伺服器上的大多數 CPU。</span><span class="sxs-lookup"><span data-stu-id="095ea-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="095ea-231">支援的負載峰值為 12/秒。</span><span class="sxs-lookup"><span data-stu-id="095ea-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="095ea-232">可持續性是由伺服器上的其他負載所決定。</span><span class="sxs-lookup"><span data-stu-id="095ea-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="095ea-233">啟動會話通常代表已登入長時間時段之使用者的登入。</span><span class="sxs-lookup"><span data-stu-id="095ea-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-234">已拒絕的撥入語音通話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="095ea-235">已拒絕的輸入通話總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-236">失敗的入站語音通話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="095ea-237">失敗的入站語音通話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-238">失敗的傳出語音通話總計</span><span class="sxs-lookup"><span data-stu-id="095ea-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="095ea-239">失敗的出站語音通話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-240">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="095ea-241">使用者終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-242">推播通知要求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="095ea-243">推播通知要求的總數量</span><span class="sxs-lookup"><span data-stu-id="095ea-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-244">[推播通知] 要求總失敗</span><span class="sxs-lookup"><span data-stu-id="095ea-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="095ea-245">失敗的推播通知請求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-246">成功的推播通知請求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="095ea-247">成功的推播通知請求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-248">限制的推播通知總要求</span><span class="sxs-lookup"><span data-stu-id="095ea-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="095ea-249">已中止的推播通知請求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-250">失敗的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="095ea-251">失敗的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-252">在命令通道上接收到的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="095ea-253">在命令通道上接收到的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-254">拒絕的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="095ea-255">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="095ea-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-256">成功總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="095ea-257">已成功完成行動服務的總請求數</span><span class="sxs-lookup"><span data-stu-id="095ea-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-258">會話啟動總計數</span><span class="sxs-lookup"><span data-stu-id="095ea-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="095ea-259">行動服務啟動後啟動的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-260">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="095ea-261">因使用者空閒超時而終止的會話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="095ea-262">成功輸入語音通話總計</span><span class="sxs-lookup"><span data-stu-id="095ea-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="095ea-263">成功的輸入通話總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="095ea-264">成功的傳出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="095ea-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="095ea-265">成功的出站通話總次數</span><span class="sxs-lookup"><span data-stu-id="095ea-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

