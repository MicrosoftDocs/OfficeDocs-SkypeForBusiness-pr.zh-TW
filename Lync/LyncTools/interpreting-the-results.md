---
title: 解釋結果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="4f041-102">解釋結果</span><span class="sxs-lookup"><span data-stu-id="4f041-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f041-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4f041-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4f041-104">Lync Server 2013 應力和效能工具（LyncPerfTool）有許多計數器，您可以用來瞭解用戶端正在執行的動作，以及是否遇到問題。</span><span class="sxs-lookup"><span data-stu-id="4f041-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="4f041-105">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="4f041-105">Client Counters</span></span>

<span data-ttu-id="4f041-106">每個執行中的 LyncPerfTool 實例都有一個單獨的計數器實例。</span><span class="sxs-lookup"><span data-stu-id="4f041-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="4f041-107">每個實例都是以其進程識別碼命名。</span><span class="sxs-lookup"><span data-stu-id="4f041-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="4f041-108">如果用戶端超載，可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="4f041-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="4f041-109">若要避免這些問題，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4f041-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="4f041-110">監視用戶端電腦上的 CPU 和記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="4f041-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="4f041-111">如果 CPU 持續超過90%，請減少使用者數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="4f041-112">如果記憶體需求量較高，您可能會在頁面檔案不夠大時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="4f041-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="4f041-113">確認確認費用未超出電腦的限制。</span><span class="sxs-lookup"><span data-stu-id="4f041-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="4f041-114">如果您正在執行記憶體限制，請考慮增加頁面檔案大小或減少使用者數量</span><span class="sxs-lookup"><span data-stu-id="4f041-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="4f041-115">下表列出重要的 LyncPerfTool 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="4f041-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="4f041-116">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-117"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-118"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-119">花費的時間（以分鐘為單位）</span><span class="sxs-lookup"><span data-stu-id="4f041-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="4f041-120">進程開始之後所花費的時間。</span><span class="sxs-lookup"><span data-stu-id="4f041-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-121">作用中端點</span><span class="sxs-lookup"><span data-stu-id="4f041-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="4f041-122">目前連線到伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-123">失敗的登錄</span><span class="sxs-lookup"><span data-stu-id="4f041-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="4f041-124">端點登入失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-125">登入嘗試</span><span class="sxs-lookup"><span data-stu-id="4f041-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="4f041-126">端點登入嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-127">端點已中斷連接</span><span class="sxs-lookup"><span data-stu-id="4f041-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="4f041-128">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-129">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-130"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-131"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-132">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="4f041-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="4f041-133">目前狀態變更嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-133">Total number of presence change attempts.</span></span> <span data-ttu-id="4f041-134">針對不同類型的目前狀態變更，請參閱 SetPresence （目前狀態類型）通話效能計數器。</span><span class="sxs-lookup"><span data-stu-id="4f041-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-135">SetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="4f041-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="4f041-136">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-137">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="4f041-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="4f041-138">[取得目前狀態] 要求嘗試的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-139">GetPresence 的 NNN 回應</span><span class="sxs-lookup"><span data-stu-id="4f041-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="4f041-140">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-141">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-141">**Address Book service Information**</span></span>

<span data-ttu-id="4f041-142">此類別包含用來監視通訊錄服務（ABS）檔案下載和通訊錄網頁查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="4f041-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-143"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-144"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-145">嘗試的 ABS 完整/增量檔案下載</span><span class="sxs-lookup"><span data-stu-id="4f041-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-146">已嘗試完整或增量檔案下載要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-147">ABS 完整/Delta 檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="4f041-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4f041-148">已嘗試完整或增量檔案下載要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-149">通訊錄 Web 查詢服務相關計數器</span><span class="sxs-lookup"><span data-stu-id="4f041-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="4f041-150">通訊錄檔案下載相關計數器。</span><span class="sxs-lookup"><span data-stu-id="4f041-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-151">嘗試 ABS 通話</span><span class="sxs-lookup"><span data-stu-id="4f041-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-152">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-153">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="4f041-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4f041-154">傳回成功回應代碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-155">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="4f041-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="4f041-156">傳回錯誤回應代碼之通訊錄 Web 查詢服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-157">**通訊群組清單（DL）資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-158"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-159"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-160">已嘗試來電</span><span class="sxs-lookup"><span data-stu-id="4f041-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-161">嘗試的通訊群組清單展開（DLX） web 服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-162">通話成功</span><span class="sxs-lookup"><span data-stu-id="4f041-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4f041-163">傳回成功回應代碼之 DLX web 服務要求的總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-164">通話失敗</span><span class="sxs-lookup"><span data-stu-id="4f041-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="4f041-165">傳回錯誤回應代碼之 DLX web 服務要求的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-166">**VoIP 基本資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="4f041-167">在啟用這些案例時，以下所列的效能計數器會列示在所有的語音 IP （VoIP）通話中，包括對轉送伺服器、A/V 會議伺服器、邊緣伺服器、回應群組應用程式，以及會議自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="4f041-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-168"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-169"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-170">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="4f041-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="4f041-171">目前正在進行的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-172">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="4f041-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="4f041-173">已終止的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-174">拒絕通話</span><span class="sxs-lookup"><span data-stu-id="4f041-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="4f041-175">已拒絕的來電通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-176">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-177">已嘗試輸入/撥出語音通話的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-178">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="4f041-179">已建立的傳入/傳出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-180">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="4f041-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="4f041-181">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-182">VoIP 傳遞率（%）</span><span class="sxs-lookup"><span data-stu-id="4f041-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="4f041-183">已建立的通話總數/嘗試的通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-184">**回應群組服務通話資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-185"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-186"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-187">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="4f041-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="4f041-188">回應群組應用程式的使用中通話總次數。</span><span class="sxs-lookup"><span data-stu-id="4f041-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-189">已嘗試來電</span><span class="sxs-lookup"><span data-stu-id="4f041-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-190">嘗試的通話總次數。</span><span class="sxs-lookup"><span data-stu-id="4f041-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-191">**立即訊息（IM）通話資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-192"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-193"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-194">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="4f041-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="4f041-195">正在進行內傳/撥出的立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-196">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="4f041-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="4f041-197">已終止傳入/傳出立即訊息通話的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-198">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="4f041-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="4f041-199">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-200">接收/傳送的 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="4f041-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="4f041-201">所有會話接收或傳送的訊息總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-202">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-203">嘗試的傳入/傳出立即訊息呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-204">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="4f041-205">已建立的傳入/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-206">**App 共用呼叫資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-207"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-208"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-209">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="4f041-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="4f041-210">正在進行中傳入/傳出應用程式共用通話的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-211">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="4f041-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="4f041-212">已終止的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-213">呼叫已收到 NNN</span><span class="sxs-lookup"><span data-stu-id="4f041-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="4f041-214">從伺服器接收的 nnn 回應碼總數目。</span><span class="sxs-lookup"><span data-stu-id="4f041-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-215">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-216">嘗試的傳入/傳出應用程式共用呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-217">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="4f041-218">已建立的傳入/傳出應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-219">**CAA 通話資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-220"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-221"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-222">使用中的通話</span><span class="sxs-lookup"><span data-stu-id="4f041-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="4f041-223">目前正在進行中的內送/出局公用電話網絡（PSTN）通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-224">呼叫終止</span><span class="sxs-lookup"><span data-stu-id="4f041-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="4f041-225">已終止的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-226">已嘗試來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="4f041-227">嘗試的傳入/傳出 PSTN 呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-228">已建立來電/撥出通話</span><span class="sxs-lookup"><span data-stu-id="4f041-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="4f041-229">已建立的傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-230">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="4f041-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-231"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-232"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-233">即時立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="4f041-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="4f041-234">即時立即訊息會議的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-235">活動音訊/視訊會議</span><span class="sxs-lookup"><span data-stu-id="4f041-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="4f041-236">正在進行的音訊/視頻（A/V）會議總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-237">使用中的應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="4f041-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="4f041-238">正在進行的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-239">參與者人數</span><span class="sxs-lookup"><span data-stu-id="4f041-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="4f041-240">目前與會議連接的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f041-241">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="4f041-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="4f041-242">嘗試排程會議時失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-243">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="4f041-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="4f041-244">嘗試連線到會議時失敗的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f041-245">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="4f041-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f041-246"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="4f041-247"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="4f041-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f041-248">成功的 IMMCU 連接總數</span><span class="sxs-lookup"><span data-stu-id="4f041-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4f041-249">已加入之立即訊息會議的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f041-250">成功的 DMCU 連接總數</span><span class="sxs-lookup"><span data-stu-id="4f041-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="4f041-251">已加入/V 會議的總數。</span><span class="sxs-lookup"><span data-stu-id="4f041-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

