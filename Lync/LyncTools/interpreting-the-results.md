---
title: 解讀結果
description: 解讀結果。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565339"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="a98dc-103">解讀結果</span><span class="sxs-lookup"><span data-stu-id="a98dc-103">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a98dc-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a98dc-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a98dc-105">Lync Server 2013 應力和效能工具 ( # A0) 有許多計數器可供您用來瞭解用戶端的執行狀況及是否發生問題。</span><span class="sxs-lookup"><span data-stu-id="a98dc-105">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="a98dc-106">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="a98dc-106">Client Counters</span></span>

<span data-ttu-id="a98dc-107">每個執行的 LyncPerfTool.exe 實例都有個別的計數器實例。</span><span class="sxs-lookup"><span data-stu-id="a98dc-107">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="a98dc-108">每個實例都會以其進程識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="a98dc-108">Each instance is named by its process ID.</span></span>

<span data-ttu-id="a98dc-109">如果用戶端超載，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="a98dc-109">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="a98dc-110">若要避免這些問題，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a98dc-110">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="a98dc-111">監視用戶端電腦上的 CPU 和記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="a98dc-111">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="a98dc-112">如果 CPU 持續超過90%，請減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a98dc-112">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="a98dc-113">如果記憶體佔用量高，您可能會遇到問題，如果頁面檔案不夠大。</span><span class="sxs-lookup"><span data-stu-id="a98dc-113">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="a98dc-114">確認認可費用未超出電腦上的限制。</span><span class="sxs-lookup"><span data-stu-id="a98dc-114">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="a98dc-115">如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數目</span><span class="sxs-lookup"><span data-stu-id="a98dc-115">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="a98dc-116">下表列出重要的 LyncPerfTool 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a98dc-116">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="a98dc-117">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-117">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-118"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-118"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-119"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-119"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-120">花費的時間（分鐘）</span><span class="sxs-lookup"><span data-stu-id="a98dc-120">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="a98dc-121">自處理常式開始所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="a98dc-121">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-122">作用中端點</span><span class="sxs-lookup"><span data-stu-id="a98dc-122">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="a98dc-123">目前連線至伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="a98dc-123">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-124">失敗登入</span><span class="sxs-lookup"><span data-stu-id="a98dc-124">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="a98dc-125">端點登入失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-125">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-126">登入嘗試</span><span class="sxs-lookup"><span data-stu-id="a98dc-126">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="a98dc-127">嘗試登入嘗試次數的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-127">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-128">中斷連線端點</span><span class="sxs-lookup"><span data-stu-id="a98dc-128">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="a98dc-129">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-129">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-130">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-130">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-131"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-131"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-132"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-132"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-133">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-133">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a98dc-134">目前狀態變更嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-134">Total number of presence change attempts.</span></span> <span data-ttu-id="a98dc-135">針對不同類型的狀態變更，請參閱 SetPresence (目前狀態類型) 通話效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a98dc-135">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-136">SetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="a98dc-136">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="a98dc-137">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-137">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-138">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-138">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a98dc-139">Get 顯示狀態要求嘗試總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-139">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-140">GetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="a98dc-140">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="a98dc-141">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-141">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-142">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-142">**Address Book service Information**</span></span>

<span data-ttu-id="a98dc-143">此類別包含用於監視通訊錄服務 (ABS) 檔案下載和通訊錄 Web 查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="a98dc-143">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-144"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-144"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-145"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-145"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-146">嘗試實際的完整/Delta 檔案下載</span><span class="sxs-lookup"><span data-stu-id="a98dc-146">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-147">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-147">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-148">ABS 完整/Delta 檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="a98dc-148">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a98dc-149">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-149">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-150">通訊錄 Web 查詢服務相關的計數器</span><span class="sxs-lookup"><span data-stu-id="a98dc-150">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="a98dc-151">通訊錄檔案下載相關的計數器。</span><span class="sxs-lookup"><span data-stu-id="a98dc-151">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-152">嘗試的 ABS WS 通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-152">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-153">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-153">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-154">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="a98dc-154">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a98dc-155">傳回成功回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-155">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-156">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="a98dc-156">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a98dc-157">傳回錯誤回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-157">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-158">**通訊群組清單 (DL) 資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-158">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-159"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-159"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-160"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-160"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-161">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="a98dc-161">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-162">嘗試之通訊群組清單擴充 (DLX) web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-162">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-163">通話成功</span><span class="sxs-lookup"><span data-stu-id="a98dc-163">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a98dc-164">傳回成功回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-164">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-165">通話失敗</span><span class="sxs-lookup"><span data-stu-id="a98dc-165">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a98dc-166">傳回錯誤回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-166">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-167">**VoIP 基本資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-167">**VoIP Basic Information**</span></span>

<span data-ttu-id="a98dc-168">在啟用這些案例時，所有 Voice over IP (VoIP) 通話（包括對轉送伺服器的呼叫、A/V 會議伺服器、Edge Server、回應群組應用程式和會議自動語音應答）的報告編號，均會列出下列效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a98dc-168">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-169"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-169"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-170"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-170"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-171">主動通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-171">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a98dc-172">目前正在進行的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-172">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-173">來電終止</span><span class="sxs-lookup"><span data-stu-id="a98dc-173">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a98dc-174">已終止傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-174">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-175">拒絕通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-175">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="a98dc-176">拒絕的傳入語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-176">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-177">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-177">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-178">嘗試傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-178">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-179">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-179">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a98dc-180">已建立的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-180">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-181">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a98dc-181">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a98dc-182">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-182">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-183">VoIP 通率 (% ) </span><span class="sxs-lookup"><span data-stu-id="a98dc-183">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="a98dc-184">已建立的通話總數/嘗試的總通話數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-184">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-185">**回應群組服務呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-185">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-186"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-186"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-187"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-187"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-188">主動通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-188">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a98dc-189">回應群組應用程式的作用中呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-189">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-190">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="a98dc-190">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-191">嘗試的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-191">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-192">**立即訊息 (IM) 呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-192">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-193"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-193"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-194"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-194"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-195">主動通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-195">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a98dc-196">進行中傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-196">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-197">來電終止</span><span class="sxs-lookup"><span data-stu-id="a98dc-197">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a98dc-198">已終止的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-198">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-199">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a98dc-199">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a98dc-200">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-200">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-201">接收/傳送的 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="a98dc-201">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="a98dc-202">所有會話中已接收或已傳送的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-202">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-203">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-203">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-204">嘗試傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-204">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-205">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-205">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a98dc-206">已建立的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-206">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-207">**應用程式共用呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-207">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-208"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-208"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-209"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-209"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-210">主動通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-210">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a98dc-211">進行中傳入/傳出應用程式共用呼叫的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-211">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-212">來電終止</span><span class="sxs-lookup"><span data-stu-id="a98dc-212">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a98dc-213">已終止的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-213">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-214">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a98dc-214">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a98dc-215">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-215">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-216">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-216">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-217">嘗試的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-217">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-218">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-218">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a98dc-219">已建立的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-219">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-220">**CAA 呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-220">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-221"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-221"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-222"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-222"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-223">主動通話</span><span class="sxs-lookup"><span data-stu-id="a98dc-223">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a98dc-224">目前 (PSTN) 通話的內送/撥出公用交換電話網路 PSTN 總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-224">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-225">來電終止</span><span class="sxs-lookup"><span data-stu-id="a98dc-225">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a98dc-226">已終止的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-226">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-227">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-227">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a98dc-228">嘗試傳入/傳出 PSTN 通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-228">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-229">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a98dc-229">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a98dc-230">已建立的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-230">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-231">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="a98dc-231">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-232"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-232"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-233"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-233"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-234">主動立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="a98dc-234">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="a98dc-235">進行中的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-235">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-236">活躍 Audio/Video 會議</span><span class="sxs-lookup"><span data-stu-id="a98dc-236">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="a98dc-237">A/V) 會議的日常音訊/視頻 (總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-237">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-238">Active Application 共用會議</span><span class="sxs-lookup"><span data-stu-id="a98dc-238">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="a98dc-239">進行中的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-239">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-240">參與者人數</span><span class="sxs-lookup"><span data-stu-id="a98dc-240">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="a98dc-241">目前連接至會議的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-241">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-242">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="a98dc-242">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="a98dc-243">嘗試排程會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-243">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-244">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="a98dc-244">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="a98dc-245">嘗試連線至會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-245">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a98dc-246">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="a98dc-246">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a98dc-247"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-247"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a98dc-248"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a98dc-248"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a98dc-249">已成功聯結的 IMMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="a98dc-249">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a98dc-250">加入的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-250">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a98dc-251">已成功聯結的 DMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="a98dc-251">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a98dc-252">加入的 A/V 會議總數。</span><span class="sxs-lookup"><span data-stu-id="a98dc-252">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

