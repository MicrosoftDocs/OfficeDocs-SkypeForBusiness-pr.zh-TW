---
title: Lync Server 2013： 行動效能計數器
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
ms.openlocfilehash: cb5363ef31f44abdb9c8ea07938668f17b95c471
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a><span data-ttu-id="14a3d-102">Lync Server 2013 中的行動效能計數器</span><span class="sxs-lookup"><span data-stu-id="14a3d-102">Mobility performance counters in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a3d-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="14a3d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="14a3d-104">下表列出的名稱和描述的效能計數器可監視執行 Unified Communications Web API (UCWA) 及 Lync Server 2013 Mcx Mobility Service 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="14a3d-104">The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Lync Server 2013 Mcx Mobility Service.</span></span>

<span data-ttu-id="14a3d-105">UCWA 表格中的計數器的類別名稱是**LS:WEB – ucwa 的參考**。</span><span class="sxs-lookup"><span data-stu-id="14a3d-105">The category name for the counters in the UCWA table is **LS:WEB – UCWA**.</span></span>

<span data-ttu-id="14a3d-106">Mcx Mobility Service 表格中的計數器的類別名稱是**LS:WEB-行動通訊服務**。</span><span class="sxs-lookup"><span data-stu-id="14a3d-106">The category name for the counters in the Mcx Mobility Service table is **LS:WEB - Mobile Communication Service**.</span></span>

<div>

## <a name="performance-counters-for-ucwa"></a><span data-ttu-id="14a3d-107">UCWA 的效能計數器</span><span class="sxs-lookup"><span data-stu-id="14a3d-107">Performance Counters for UCWA</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a3d-108">計數器</span><span class="sxs-lookup"><span data-stu-id="14a3d-108">Counter</span></span></th>
<th><span data-ttu-id="14a3d-109">描述</span><span class="sxs-lookup"><span data-stu-id="14a3d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-110">作用中的應用程式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-110">Active Application Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-111">目前的應用程式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-111">The current number of applications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-112">使用中應用程式共用形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-112">Active Application Sharing Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-113">目前應用程式共用形式的數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-113">The current number of Application Sharing modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-114">主動音訊形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-114">Active Audio Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-115">目前音訊形式的數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-115">The current number of Audio modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-116">作用中資料共同作業形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-116">Active Data Collaboration Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-117">目前的資料共同作業形式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-117">The current number of Data Collaboration modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-118">Active Directory 相片取得延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="14a3d-118">Active Directory Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="14a3d-119">此計數器會顯示平均時間 （以毫秒為單位） 來擷取將相片從 active directory</span><span class="sxs-lookup"><span data-stu-id="14a3d-119">This counter shows the average time (in milliseconds) to retrieve a photo from active directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-120">作用中郵件的形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-120">Active Messaging Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-121">目前的通訊形式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-121">The current number of Messaging modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-122">作用中的全景視訊形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-122">Active Panoramic Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-123">目前的全景視訊形式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-123">The current number of Panoramic Video modality</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-124">使用中擱置 Get 計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-124">Active Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-125">擱置取得; 目前作用中的數字長期保留的伺服器連線</span><span class="sxs-lookup"><span data-stu-id="14a3d-125">The number of currently active pending gets; long-held connections to the server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-126">Active Session Count</span><span class="sxs-lookup"><span data-stu-id="14a3d-126">Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-127">目前的每個應用程式及總計 UCWA 中註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-127">The current number of endpoints registered in UCWA per application and total</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-128">作用中使用者執行個體計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-128">Active User Instance Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-129">目前的使用者執行個體數</span><span class="sxs-lookup"><span data-stu-id="14a3d-129">The current number of user instances</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-130">作用中使用者沒有應用程式的執行個體</span><span class="sxs-lookup"><span data-stu-id="14a3d-130">Active User Instances without Application</span></span></p></td>
<td><p><span data-ttu-id="14a3d-131">目前的使用者沒有應用程式的執行個體數</span><span class="sxs-lookup"><span data-stu-id="14a3d-131">The current number of user instances without application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-132">主動影片形式計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-132">Active Video Modality Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-133">目前的影片形式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-133">The current number of Video modality</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-134">應用程式建立要求接收/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-134">Application Creation Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-135">每秒接收應用程式建立要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-135">The per second rate of received application creation requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-136">為 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-136">AS MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-137">AS MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-137">The number of AS MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-138">AV MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-138">AV MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-139">AV MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-139">The number of AV MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-140">平均應用程式啟動時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="14a3d-140">Average Application Startup Time (ms)</span></span></p></td>
<td><p><span data-ttu-id="14a3d-141">平均應用程式啟動時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="14a3d-141">The average application startup time in Milliseconds</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-142">平均存留期 （毫秒） 的工作階段</span><span class="sxs-lookup"><span data-stu-id="14a3d-142">Average Lifetime for Session (ms)</span></span></p></td>
<td><p><span data-ttu-id="14a3d-143">以毫秒為單位的工作階段平均存留期</span><span class="sxs-lookup"><span data-stu-id="14a3d-143">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-144">資料 MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-144">Data MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-145">資料 MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-145">The number of Data MCU Join Failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-146">Exchange 連絡人搜尋延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="14a3d-146">Exchange Contact Search Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="14a3d-147">此計數器會顯示平均時間 （以毫秒為單位） 若要在 Exchange 中搜尋連絡人</span><span class="sxs-lookup"><span data-stu-id="14a3d-147">This counter shows the average time (in milliseconds) to search contact in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-148">Exchange HD 相片 Get 延遲 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="14a3d-148">Exchange HD Photo Get Latency (ms)</span></span></p></td>
<td><p><span data-ttu-id="14a3d-149">此計數器會顯示平均時間 （以毫秒為單位） 從 Exchange 擷取相片</span><span class="sxs-lookup"><span data-stu-id="14a3d-149">This counter shows the average time (in milliseconds) to retrieve a photo from Exchange</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-150">HTTP 4xx 回應/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-150">HTTP 4xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-151">每秒的 HTTP 4xx 碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-151">The per second rate of responses with HTTP 4xx code</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-152">HTTP 5xx 回應/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-152">HTTP 5xx Responses/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-153">每秒的 HTTP 5xx 碼回應的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-153">The per second rate of responses with HTTP 5xx code</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-154">IM MCU 加入失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-154">IM MCU Join Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-155">IM MCU 加入失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-155">The number of IM MCU Join Failures</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-156">Active Directory 相片取得失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-156">Number of Active Directory Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-157">若要從 Active Directory 擷取相片的失敗總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-157">The total number of failures to retrieve photos from Active Directory</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-158">連絡人搜尋失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-158">Number of Contact Search failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-159">若要在 Exchange 中搜尋連絡人的失敗總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-159">The total number of failures to search contacts in Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-160">還原序列化失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-160">Number of Deserialization Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-161">還原序列化失敗總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-161">The total number of deserialization failures</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-162">HD 相片取得失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-162">Number of HD Photo Get Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-163">若要從 Exchange 擷取 HD 相片的失敗總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-163">The total number of failures to retrieve HD photos from Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-164">對每個應用程式的最大訂閱</span><span class="sxs-lookup"><span data-stu-id="14a3d-164">Over The Maximum Subscriptions Per Application</span></span></p></td>
<td><p><span data-ttu-id="14a3d-165">訂閱要求，透過允許每個應用程式的最大數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-165">The number of Subscription requests over the maximum allowed per application</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-166">對每個批次的最大訂閱</span><span class="sxs-lookup"><span data-stu-id="14a3d-166">Over The Maximum Subscriptions Per Batch</span></span></p></td>
<td><p><span data-ttu-id="14a3d-167">透過最大允許每個批次訂閱要求數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-167">The number of Subscription requests over the maximum allowed per batch</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-168">目前狀態訂閱失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-168">Presence Subscription Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-169">若要訂閱目前狀態的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-169">The number of failures to subscribe presence</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-170">註冊的端點失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-170">Registering Endpoint Failures</span></span></p></td>
<td><p><span data-ttu-id="14a3d-171">若要註冊端點失敗的次數</span><span class="sxs-lookup"><span data-stu-id="14a3d-171">The number of failures to register endpoints</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-172">要求接收/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-172">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-173">每秒接收要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-173">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-174">要求成功/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-174">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-175">每秒成功的要求 （HTTP 2xx/3xx 回應碼） 的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-175">The per second rate of successful requests (HTTP 2xx/3xx response codes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-176">成功建立應用程式要求數/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-176">Succeeded Create Application Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-177">每秒成功的應用程式建立要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-177">The per second rate of successful application creation requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-178">暫止的 Get 計數逾時</span><span class="sxs-lookup"><span data-stu-id="14a3d-178">Timed Out Pending Get Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-179">等候逾時取得的數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-179">The number of pending gets that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-180">接收到的總應用程式建立要求</span><span class="sxs-lookup"><span data-stu-id="14a3d-180">Total Application Creation Requests Received</span></span></p></td>
<td><p><span data-ttu-id="14a3d-181">自從服務啟動以來所收到的應用程式建立要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-181">The total number of application creation requests received since the service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-182">總 HTTP 4xx 回應</span><span class="sxs-lookup"><span data-stu-id="14a3d-182">Total HTTP 4xx Responses</span></span></p></td>
<td><p><span data-ttu-id="14a3d-183">HTTP 4xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-183">The total number of HTTP 4xx responses</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-184">總 HTTP 5xx 回應</span><span class="sxs-lookup"><span data-stu-id="14a3d-184">Total HTTP 5xx Responses</span></span></p></td>
<td><p><span data-ttu-id="14a3d-185">HTTP 5xx 回應總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-185">The total number of HTTP 5xx responses</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-186">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-186">Total Requests Received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="14a3d-187">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-187">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-188">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-188">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="14a3d-189">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-189">The total number of requests that succeeded</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-190">起始的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-190">Total Sessions Initiated</span></span></p></td>
<td><p><span data-ttu-id="14a3d-191">自服務啟動後已起始的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-191">The total number of sessions that were initiated since the service was started</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-192">因為閒置逾時終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-192">Total Sessions Terminated Because of Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="14a3d-193">由於使用者閒置逾時而終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-193">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-194">總節流應用程式</span><span class="sxs-lookup"><span data-stu-id="14a3d-194">Total Throttled Applications</span></span></p></td>
<td><p><span data-ttu-id="14a3d-195">節流應用程式數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-195">The number of throttled applications</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a><span data-ttu-id="14a3d-196">Mcx Mobility Service 的效能計數器</span><span class="sxs-lookup"><span data-stu-id="14a3d-196">Performance Counters for Mcx Mobility Service</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a3d-197">計數器</span><span class="sxs-lookup"><span data-stu-id="14a3d-197">Counter</span></span></th>
<th><span data-ttu-id="14a3d-198">描述</span><span class="sxs-lookup"><span data-stu-id="14a3d-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-199">以毫秒為單位的工作階段的平均存留期</span><span class="sxs-lookup"><span data-stu-id="14a3d-199">Average Lifetime for a Session in Milliseconds</span></span></p></td>
<td><p><span data-ttu-id="14a3d-200">以毫秒為單位的工作階段平均存留期</span><span class="sxs-lookup"><span data-stu-id="14a3d-200">The average lifetime for a session in milliseconds</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-201">目前的推播通知訂閱</span><span class="sxs-lookup"><span data-stu-id="14a3d-201">Current Push Notification Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="14a3d-202">目前的推播通知訂閱數目。</span><span class="sxs-lookup"><span data-stu-id="14a3d-202">The current number of push notification subscriptions.</span></span> <span data-ttu-id="14a3d-203">此數字，搭配使用 Currently Active Session Count，代表目前使用中的工作階段並登錄 Windows Mobile 或 iPhone 裝置的子集。</span><span class="sxs-lookup"><span data-stu-id="14a3d-203">This number, in conjunction with Currently Active Session Count, represents the subset of currently active sessions that are registered for Windows Mobile or iPhone devices.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-204">目前使用中網路逾時投票計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-204">Currently Active Network Timeout Poll Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-205">逾時的網路輪詢數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-205">The number of network polls that timed out</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-206">目前作用中投票計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-206">Currently Active Poll Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-207">目前使用中的輪詢 （長期保留的伺服器連線） 的數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-207">The number of currently active polls (long-held connections to the server)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-208">Currently Active Session Count</span><span class="sxs-lookup"><span data-stu-id="14a3d-208">Currently Active Session Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-209">目前在 Mobility Service 中註冊的端點數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-209">Current number of endpoints registered in the Mobility Service</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-210">目前 Active Session Count with Active 目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="14a3d-210">Currently Active Session Count with Active Presence Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="14a3d-211">目前使用中的工作階段與作用中的目前狀態訂閱數目</span><span class="sxs-lookup"><span data-stu-id="14a3d-211">The number of currently active sessions with active presence subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-212">失敗的推入通知要求數/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-212">Push Notification Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-213">每秒的失敗的推入通知速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-213">The per second rate of failed push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-214">成功的推入通知要求數/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-214">Push Notification Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-215">每秒成功的推入通知的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-215">The per second rate of successful push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-216">推入通知要求節流/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-216">Push Notification Requests Throttled/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-217">每秒的節流的推入通知速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-217">The per second rate of throttled push notifications</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-218">推入通知要求數/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-218">Push Notification Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-219">每秒傳送推入通知的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-219">The per second rate of sent push notifications</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-220">要求失敗/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-220">Requests Failed/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-221">每秒的失敗的要求速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-221">The per second rate of failed requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-222">要求接收/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-222">Requests Received/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-223">每秒接收要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-223">The per second rate of received requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-224">要求拒絕/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-224">Requests Rejected/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-225">每秒拒絕要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-225">The per second rate of rejected requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-226">要求成功/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-226">Requests Succeeded/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-227">每秒成功的要求的速率</span><span class="sxs-lookup"><span data-stu-id="14a3d-227">The per second rate of successful requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-228">已成功啟動工作階段要求數/秒</span><span class="sxs-lookup"><span data-stu-id="14a3d-228">Succeeded Initiate Session Requests/Second</span></span></p></td>
<td><p><span data-ttu-id="14a3d-229">每秒成功取得位置的速率要求。</span><span class="sxs-lookup"><span data-stu-id="14a3d-229">The per second rate of successful Get Location requests.</span></span> <span data-ttu-id="14a3d-230">若要啟動工作階段要求消耗最多的 cpu 資源，在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="14a3d-230">Requests to initiate a session consume the most CPU on the server.</span></span> <span data-ttu-id="14a3d-231">支援的尖峰負載是 12/秒。</span><span class="sxs-lookup"><span data-stu-id="14a3d-231">Peak supported load is 12/second.</span></span> <span data-ttu-id="14a3d-232">永續取決於伺服器上的其他負載。</span><span class="sxs-lookup"><span data-stu-id="14a3d-232">Sustainability depends on other loads on the server.</span></span> <span data-ttu-id="14a3d-233">起始工作階段通常表示登入已擴充的一段時間登出使用者。</span><span class="sxs-lookup"><span data-stu-id="14a3d-233">Initiate a session typically means a sign-in for a user that has been signed out for an extended period of time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-234">總拒絕撥入的語音通話</span><span class="sxs-lookup"><span data-stu-id="14a3d-234">Total Declined Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="14a3d-235">拒絕的撥入的語音通話的總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-235">The total number of inbound voice calls that were declined</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-236">失敗的撥入的語音通話總計</span><span class="sxs-lookup"><span data-stu-id="14a3d-236">Total Failed Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="14a3d-237">失敗的撥入的語音通話總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-237">The total number of inbound voice calls that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-238">總失敗的撥出語音通話</span><span class="sxs-lookup"><span data-stu-id="14a3d-238">Total Failed Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="14a3d-239">失敗的撥出語音通話總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-239">The total number of outbound voice calls that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-240">由使用者終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-240">Total number of sessions terminated by user</span></span></p></td>
<td><p><span data-ttu-id="14a3d-241">使用者終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-241">The total number of sessions terminated by users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-242">總數的推入通知要求</span><span class="sxs-lookup"><span data-stu-id="14a3d-242">Total Push Notification Requests</span></span></p></td>
<td><p><span data-ttu-id="14a3d-243">推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-243">The total number of push notification requests</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-244">總數的推入通知要求失敗</span><span class="sxs-lookup"><span data-stu-id="14a3d-244">Total Push Notification Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="14a3d-245">失敗的推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-245">The total number of push notification requests that failed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-246">成功的總數的推入通知要求</span><span class="sxs-lookup"><span data-stu-id="14a3d-246">Total Push Notification Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="14a3d-247">成功的推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-247">The total number of push notification requests that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-248">總數的推入通知要求節流</span><span class="sxs-lookup"><span data-stu-id="14a3d-248">Total Push Notification Requests Throttled</span></span></p></td>
<td><p><span data-ttu-id="14a3d-249">流速的推入通知要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-249">The total number of push notification requests that were throttled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-250">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-250">Total Requests Failed</span></span></p></td>
<td><p><span data-ttu-id="14a3d-251">失敗的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-251">The total number of requests that failed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-252">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-252">Total Requests received on the Command Channel</span></span></p></td>
<td><p><span data-ttu-id="14a3d-253">命令通道上接收的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-253">The total number of requests received on the command channel</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-254">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-254">Total Requests Rejected</span></span></p></td>
<td><p><span data-ttu-id="14a3d-255">拒絕的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-255">The total number of requests that were rejected</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-256">成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-256">Total Requests Succeeded</span></span></p></td>
<td><p><span data-ttu-id="14a3d-257">對 Mobility Service 成功的要求總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-257">The total number of requests made to the Mobility Service that succeeded</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-258">工作階段總計起始計數</span><span class="sxs-lookup"><span data-stu-id="14a3d-258">Total Session Initiated Count</span></span></p></td>
<td><p><span data-ttu-id="14a3d-259">啟動 Mobility Service 後已起始的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-259">The total number of sessions that were initiated since the Mobility Service was started</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-260">由於使用者閒置逾終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-260">Total Sessions Terminated Because of User Idle Timeout</span></span></p></td>
<td><p><span data-ttu-id="14a3d-261">由於使用者閒置逾時而終止的工作階段總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-261">The total number of sessions that were terminated because of user idle timeout</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a3d-262">總成功的撥入的語音通話</span><span class="sxs-lookup"><span data-stu-id="14a3d-262">Total Successful Inbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="14a3d-263">撥入的語音通話的成功總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-263">The total number of inbound voice calls that were successful</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a3d-264">總成功的撥出語音通話</span><span class="sxs-lookup"><span data-stu-id="14a3d-264">Total Successful Outbound Voice Calls</span></span></p></td>
<td><p><span data-ttu-id="14a3d-265">撥出語音通話的成功總數</span><span class="sxs-lookup"><span data-stu-id="14a3d-265">The total number of outbound voice calls that were successful</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

