---
title: 解讀結果
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
ms.openlocfilehash: f3a15880de861b850d3e0355491e85219ba3579d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499910"
---
# <a name="interpreting-the-results"></a><span data-ttu-id="a382c-102">解讀結果</span><span class="sxs-lookup"><span data-stu-id="a382c-102">Interpreting the Results</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a382c-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a382c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a382c-104">Lync Server 2013 應力和效能工具 ( # A0) 有許多計數器可供您用來瞭解用戶端的執行狀況及是否發生問題。</span><span class="sxs-lookup"><span data-stu-id="a382c-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="a382c-105">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="a382c-105">Client Counters</span></span>

<span data-ttu-id="a382c-106">每個執行的 LyncPerfTool.exe 實例都有個別的計數器實例。</span><span class="sxs-lookup"><span data-stu-id="a382c-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="a382c-107">每個實例都會以其進程識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="a382c-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="a382c-108">如果用戶端超載，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="a382c-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="a382c-109">若要避免這些問題，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a382c-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="a382c-110">監視用戶端電腦上的 CPU 和記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="a382c-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="a382c-111">如果 CPU 持續超過90%，請減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="a382c-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="a382c-112">如果記憶體佔用量高，您可能會遇到問題，如果頁面檔案不夠大。</span><span class="sxs-lookup"><span data-stu-id="a382c-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="a382c-113">確認認可費用未超出電腦上的限制。</span><span class="sxs-lookup"><span data-stu-id="a382c-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="a382c-114">如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數目</span><span class="sxs-lookup"><span data-stu-id="a382c-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="a382c-115">下表列出重要的 LyncPerfTool 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a382c-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="a382c-116">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-117"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-118"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-119">花費的時間（分鐘）</span><span class="sxs-lookup"><span data-stu-id="a382c-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="a382c-120">自處理常式開始所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="a382c-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-121">作用中端點</span><span class="sxs-lookup"><span data-stu-id="a382c-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="a382c-122">目前連線至伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="a382c-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-123">失敗登入</span><span class="sxs-lookup"><span data-stu-id="a382c-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="a382c-124">端點登入失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-125">登入嘗試</span><span class="sxs-lookup"><span data-stu-id="a382c-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="a382c-126">嘗試登入嘗試次數的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-127">中斷連線端點</span><span class="sxs-lookup"><span data-stu-id="a382c-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="a382c-128">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-129">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-130"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-131"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-132">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a382c-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a382c-133">目前狀態變更嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-133">Total number of presence change attempts.</span></span> <span data-ttu-id="a382c-134">針對不同類型的狀態變更，請參閱 SetPresence (目前狀態類型) 通話效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a382c-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-135">SetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="a382c-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="a382c-136">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-137">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a382c-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a382c-138">Get 顯示狀態要求嘗試總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-139">GetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="a382c-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="a382c-140">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-141">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-141">**Address Book service Information**</span></span>

<span data-ttu-id="a382c-142">此類別包含用於監視通訊錄服務 (ABS) 檔案下載和通訊錄 Web 查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="a382c-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-143"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-144"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-145">嘗試實際的完整/Delta 檔案下載</span><span class="sxs-lookup"><span data-stu-id="a382c-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-146">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-147">ABS 完整/Delta 檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="a382c-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a382c-148">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-149">通訊錄 Web 查詢服務相關的計數器</span><span class="sxs-lookup"><span data-stu-id="a382c-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="a382c-150">通訊錄檔案下載相關的計數器。</span><span class="sxs-lookup"><span data-stu-id="a382c-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-151">嘗試的 ABS WS 通話</span><span class="sxs-lookup"><span data-stu-id="a382c-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-152">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-153">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="a382c-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a382c-154">傳回成功回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-155">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="a382c-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a382c-156">傳回錯誤回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-157">**通訊群組清單 (DL) 資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-158"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-159"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-160">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="a382c-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-161">嘗試之通訊群組清單擴充 (DLX) web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-162">通話成功</span><span class="sxs-lookup"><span data-stu-id="a382c-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a382c-163">傳回成功回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-164">通話失敗</span><span class="sxs-lookup"><span data-stu-id="a382c-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a382c-165">傳回錯誤回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-166">**VoIP 基本資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="a382c-167">在啟用這些案例時，所有 Voice over IP (VoIP) 通話（包括對轉送伺服器的呼叫、A/V 會議伺服器、Edge Server、回應群組應用程式和會議自動語音應答）的報告編號，均會列出下列效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a382c-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-168"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-169"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-170">主動通話</span><span class="sxs-lookup"><span data-stu-id="a382c-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a382c-171">目前正在進行的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-172">來電終止</span><span class="sxs-lookup"><span data-stu-id="a382c-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a382c-173">已終止傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-174">拒絕通話</span><span class="sxs-lookup"><span data-stu-id="a382c-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="a382c-175">拒絕的傳入語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-176">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-177">嘗試傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-178">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a382c-179">已建立的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-180">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a382c-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a382c-181">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-182">VoIP 通率 (% ) </span><span class="sxs-lookup"><span data-stu-id="a382c-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="a382c-183">已建立的通話總數/嘗試的總通話數。</span><span class="sxs-lookup"><span data-stu-id="a382c-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-184">**回應群組服務呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-185"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-186"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-187">主動通話</span><span class="sxs-lookup"><span data-stu-id="a382c-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a382c-188">回應群組應用程式的作用中呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-189">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="a382c-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-190">嘗試的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-191">**立即訊息 (IM) 呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-192"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-193"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-194">主動通話</span><span class="sxs-lookup"><span data-stu-id="a382c-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a382c-195">進行中傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-196">來電終止</span><span class="sxs-lookup"><span data-stu-id="a382c-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a382c-197">已終止的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-198">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a382c-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a382c-199">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-200">接收/傳送的 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="a382c-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="a382c-201">所有會話中已接收或已傳送的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-202">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-203">嘗試傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-204">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a382c-205">已建立的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-206">**應用程式共用呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-207"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-208"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-209">主動通話</span><span class="sxs-lookup"><span data-stu-id="a382c-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a382c-210">進行中傳入/傳出應用程式共用呼叫的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-211">來電終止</span><span class="sxs-lookup"><span data-stu-id="a382c-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a382c-212">已終止的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-213">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a382c-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a382c-214">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-215">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-216">嘗試的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-217">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a382c-218">已建立的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-219">**CAA 呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-220"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-221"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-222">主動通話</span><span class="sxs-lookup"><span data-stu-id="a382c-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a382c-223">目前 (PSTN) 通話的內送/撥出公用交換電話網路 PSTN 總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-224">來電終止</span><span class="sxs-lookup"><span data-stu-id="a382c-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a382c-225">已終止的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-226">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a382c-227">嘗試傳入/傳出 PSTN 通話的總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-228">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="a382c-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a382c-229">已建立的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-230">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="a382c-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-231"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-232"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-233">主動立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="a382c-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="a382c-234">進行中的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-235">活躍 Audio/Video 會議</span><span class="sxs-lookup"><span data-stu-id="a382c-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="a382c-236">A/V) 會議的日常音訊/視頻 (總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-237">Active Application 共用會議</span><span class="sxs-lookup"><span data-stu-id="a382c-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="a382c-238">進行中的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-239">參與者人數</span><span class="sxs-lookup"><span data-stu-id="a382c-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="a382c-240">目前連接至會議的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a382c-241">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="a382c-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="a382c-242">嘗試排程會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-243">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="a382c-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="a382c-244">嘗試連線至會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a382c-245">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="a382c-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a382c-246"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a382c-247"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a382c-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a382c-248">已成功聯結的 IMMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="a382c-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a382c-249">加入的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a382c-250">已成功聯結的 DMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="a382c-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a382c-251">加入的 A/V 會議總數。</span><span class="sxs-lookup"><span data-stu-id="a382c-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

