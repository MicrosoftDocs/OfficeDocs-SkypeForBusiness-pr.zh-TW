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
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="cdf30-102">解讀結果</span><span class="sxs-lookup"><span data-stu-id="cdf30-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdf30-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cdf30-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cdf30-104">Lync Server 2013 應力和效能工具（LyncPerfTool.exe）具有許多計數器，您可以用來瞭解用戶端的執行狀況及是否發生問題。</span><span class="sxs-lookup"><span data-stu-id="cdf30-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="cdf30-105">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="cdf30-105">Client Counters</span></span>

<span data-ttu-id="cdf30-106">每個執行的 LyncPerfTool.exe 實例都有個別的計數器實例。</span><span class="sxs-lookup"><span data-stu-id="cdf30-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="cdf30-107">每個實例都會以其進程識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="cdf30-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="cdf30-108">如果用戶端超載，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="cdf30-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="cdf30-109">若要避免這些問題，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cdf30-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="cdf30-110">監視用戶端電腦上的 CPU 和記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="cdf30-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="cdf30-111">如果 CPU 持續超過90%，請減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="cdf30-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="cdf30-112">如果記憶體佔用量高，您可能會遇到問題，如果頁面檔案不夠大。</span><span class="sxs-lookup"><span data-stu-id="cdf30-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="cdf30-113">確認認可費用未超出電腦上的限制。</span><span class="sxs-lookup"><span data-stu-id="cdf30-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="cdf30-114">如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數目</span><span class="sxs-lookup"><span data-stu-id="cdf30-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="cdf30-115">下表列出重要的 LyncPerfTool 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="cdf30-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="cdf30-116">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-117"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-118"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-119">花費的時間（分鐘）</span><span class="sxs-lookup"><span data-stu-id="cdf30-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="cdf30-120">自處理常式開始所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="cdf30-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-121">作用中端點</span><span class="sxs-lookup"><span data-stu-id="cdf30-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="cdf30-122">目前連線至伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="cdf30-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-123">失敗登入</span><span class="sxs-lookup"><span data-stu-id="cdf30-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="cdf30-124">端點登入失敗總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-125">登入嘗試</span><span class="sxs-lookup"><span data-stu-id="cdf30-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="cdf30-126">嘗試登入嘗試次數的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-127">中斷連線端點</span><span class="sxs-lookup"><span data-stu-id="cdf30-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="cdf30-128">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-129">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-130"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-131"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-132">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="cdf30-133">目前狀態變更嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-133">Total number of presence change attempts.</span></span> <span data-ttu-id="cdf30-134">針對不同類型的狀態變更，請參閱 SetPresence （顯示狀態類型） [呼叫效能計數器]。</span><span class="sxs-lookup"><span data-stu-id="cdf30-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-135">SetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="cdf30-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="cdf30-136">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-137">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="cdf30-138">Get 顯示狀態要求嘗試總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-139">GetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="cdf30-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="cdf30-140">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-141">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-141">**Address Book service Information**</span></span>

<span data-ttu-id="cdf30-142">此類別包含用於監視通訊錄服務（ABS）檔案下載和通訊錄 Web 查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="cdf30-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-143"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-144"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-145">嘗試實際的完整/Delta 檔案下載</span><span class="sxs-lookup"><span data-stu-id="cdf30-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-146">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-147">ABS 完整/Delta 檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="cdf30-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="cdf30-148">所嘗試的完整或增量檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-149">通訊錄 Web 查詢服務相關的計數器</span><span class="sxs-lookup"><span data-stu-id="cdf30-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="cdf30-150">通訊錄檔案下載相關的計數器。</span><span class="sxs-lookup"><span data-stu-id="cdf30-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-151">嘗試的 ABS WS 通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-152">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-153">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="cdf30-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="cdf30-154">傳回成功回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-155">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="cdf30-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="cdf30-156">傳回錯誤回應碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-157">**通訊群組清單（DL）資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-158"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-159"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-160">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="cdf30-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-161">嘗試的通訊群組清單擴充（DLX） web 服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-162">通話成功</span><span class="sxs-lookup"><span data-stu-id="cdf30-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="cdf30-163">傳回成功回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-164">通話失敗</span><span class="sxs-lookup"><span data-stu-id="cdf30-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="cdf30-165">傳回錯誤回應碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-166">**VoIP 基本資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="cdf30-167">在啟用這些案例時，下列的效能計數器會列出所有 Voice over IP （VoIP）通話（包括對轉送伺服器的呼叫、A/V 會議伺服器、Edge Server、回應群組應用程式和會議自動語音應答）。</span><span class="sxs-lookup"><span data-stu-id="cdf30-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-168"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-169"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-170">主動通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="cdf30-171">目前正在進行的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-172">來電終止</span><span class="sxs-lookup"><span data-stu-id="cdf30-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="cdf30-173">已終止傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-174">拒絕通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="cdf30-175">拒絕的傳入語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-176">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-177">嘗試傳入/傳出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-178">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="cdf30-179">已建立的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-180">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="cdf30-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="cdf30-181">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-182">VoIP 通過率（%）</span><span class="sxs-lookup"><span data-stu-id="cdf30-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="cdf30-183">已建立的通話總數/嘗試的總通話數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-184">**回應群組服務呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-185"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-186"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-187">主動通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="cdf30-188">回應群組應用程式的作用中呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-189">嘗試的來電</span><span class="sxs-lookup"><span data-stu-id="cdf30-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-190">嘗試的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-191">**立即訊息（IM）通話資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-192"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-193"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-194">主動通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="cdf30-195">進行中傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-196">來電終止</span><span class="sxs-lookup"><span data-stu-id="cdf30-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="cdf30-197">已終止的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-198">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="cdf30-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="cdf30-199">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-200">接收/傳送的 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="cdf30-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="cdf30-201">所有會話中已接收或已傳送的郵件總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-202">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-203">嘗試傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-204">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="cdf30-205">已建立的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-206">**應用程式共用呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-207"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-208"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-209">主動通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="cdf30-210">進行中傳入/傳出應用程式共用呼叫的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-211">來電終止</span><span class="sxs-lookup"><span data-stu-id="cdf30-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="cdf30-212">已終止的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-213">呼叫已接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="cdf30-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="cdf30-214">從伺服器接收的 nnn 回應碼總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-215">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-216">嘗試的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-217">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="cdf30-218">已建立的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-219">**CAA 呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-220"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-221"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-222">主動通話</span><span class="sxs-lookup"><span data-stu-id="cdf30-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="cdf30-223">目前正在進行的內送/撥出公用電話網絡（PSTN）通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-224">來電終止</span><span class="sxs-lookup"><span data-stu-id="cdf30-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="cdf30-225">已終止的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-226">嘗試傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="cdf30-227">嘗試傳入/傳出 PSTN 通話的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-228">已建立傳入/撥出電話</span><span class="sxs-lookup"><span data-stu-id="cdf30-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="cdf30-229">已建立的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-230">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="cdf30-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-231"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-232"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-233">主動立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="cdf30-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="cdf30-234">進行中的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-235">活躍 Audio/Video 會議</span><span class="sxs-lookup"><span data-stu-id="cdf30-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="cdf30-236">進行中音訊/視頻（A/V）會議的總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-237">Active Application 共用會議</span><span class="sxs-lookup"><span data-stu-id="cdf30-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="cdf30-238">進行中的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-239">參與者人數</span><span class="sxs-lookup"><span data-stu-id="cdf30-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="cdf30-240">目前連接至會議的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-241">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="cdf30-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="cdf30-242">嘗試排程會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-243">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="cdf30-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="cdf30-244">嘗試連線至會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cdf30-245">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="cdf30-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdf30-246"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="cdf30-247"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="cdf30-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdf30-248">已成功聯結的 IMMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="cdf30-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="cdf30-249">加入的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdf30-250">已成功聯結的 DMCU 聯接總數</span><span class="sxs-lookup"><span data-stu-id="cdf30-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="cdf30-251">加入的 A/V 會議總數。</span><span class="sxs-lookup"><span data-stu-id="cdf30-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

