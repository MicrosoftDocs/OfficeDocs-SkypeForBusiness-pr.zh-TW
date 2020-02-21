---
title: 解譯結果
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3683e2a2ac9fb163fe9db3dabce40b3c61d098
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a><span data-ttu-id="a51a7-102">解譯結果</span><span class="sxs-lookup"><span data-stu-id="a51a7-102">Interpreting the Results</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51a7-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="a51a7-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a51a7-104">Lync Server 2013 壓力及效能工具 (LyncPerfTool.exe) 具有您可以使用來了解用戶端所做的動作，以及是否發生問題的許多計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-104">The Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) has many counters that you can use to understand what the client is doing and whether it is encountering issues.</span></span>

<div>

## <a name="client-counters"></a><span data-ttu-id="a51a7-105">用戶端計數器</span><span class="sxs-lookup"><span data-stu-id="a51a7-105">Client Counters</span></span>

<span data-ttu-id="a51a7-106">每個執行個體正在執行的 LyncPerfTool.exe 有獨立的執行個體的計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-106">Each instance of LyncPerfTool.exe that is running has a separate instance of the counters.</span></span> <span data-ttu-id="a51a7-107">每個執行個體是名為其處理程序識別碼。</span><span class="sxs-lookup"><span data-stu-id="a51a7-107">Each instance is named by its process ID.</span></span>

<span data-ttu-id="a51a7-108">如果用戶端屬於多載，可以發生問題。</span><span class="sxs-lookup"><span data-stu-id="a51a7-108">If the clients are overloaded, issues can occur.</span></span> <span data-ttu-id="a51a7-109">若要避免這些問題，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="a51a7-109">To prevent these issues, do the following:</span></span>

1.  <span data-ttu-id="a51a7-110">監視 CPU 及記憶體使用量的用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="a51a7-110">Monitor the CPU and the memory usage on the client computers.</span></span> <span data-ttu-id="a51a7-111">如果 CPU 持續超過百分之 90，降低使用者的數目。</span><span class="sxs-lookup"><span data-stu-id="a51a7-111">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>

2.  <span data-ttu-id="a51a7-112">如果記憶體耗用量為高，您可能會遇到問題如果分頁檔不是夠大。</span><span class="sxs-lookup"><span data-stu-id="a51a7-112">If the memory footprint is high, you could run into issues if the page file is not big enough.</span></span> <span data-ttu-id="a51a7-113">確認認可費用未達到次之電腦上的限制。</span><span class="sxs-lookup"><span data-stu-id="a51a7-113">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="a51a7-114">如果您執行到記憶體限制，請考慮增加分頁檔案大小或降低的使用者數目</span><span class="sxs-lookup"><span data-stu-id="a51a7-114">If you are running into memory limits, consider increasing the page file size or reducing the number of users</span></span>

<span data-ttu-id="a51a7-115">下表列出的索引鍵的 LyncPerfTool 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-115">The following tables list the key LyncPerfTool performance counters.</span></span>

<span data-ttu-id="a51a7-116">**一般資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-116">**General Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-117"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-117"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-118"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-118"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-119">以分鐘為單位所花費的時間</span><span class="sxs-lookup"><span data-stu-id="a51a7-119">Time Spent in Minutes</span></span></p></td>
<td><p><span data-ttu-id="a51a7-120">啟動程序後，所需時間。</span><span class="sxs-lookup"><span data-stu-id="a51a7-120">Time spent since the process was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-121">作用中的端點</span><span class="sxs-lookup"><span data-stu-id="a51a7-121">Active Endpoints</span></span></p></td>
<td><p><span data-ttu-id="a51a7-122">目前連接至伺服器的端點數目。</span><span class="sxs-lookup"><span data-stu-id="a51a7-122">Number of endpoints currently connected to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-123">登入失敗</span><span class="sxs-lookup"><span data-stu-id="a51a7-123">Failed Logons</span></span></p></td>
<td><p><span data-ttu-id="a51a7-124">端點登入失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-124">Total number of endpoint sign-in failures.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-125">登入嘗試次數</span><span class="sxs-lookup"><span data-stu-id="a51a7-125">Logon Attempts</span></span></p></td>
<td><p><span data-ttu-id="a51a7-126">嘗試登入的端點總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-126">Total number of endpoint sign-in attempts.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-127">中斷連線的端點</span><span class="sxs-lookup"><span data-stu-id="a51a7-127">Endpoints Disconnected</span></span></p></td>
<td><p><span data-ttu-id="a51a7-128">已中斷連線的端點總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-128">Total number of endpoints that have been disconnected.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-129">**目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-129">**Presence Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-130"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-130"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-131"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-131"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-132">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-132">SetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a51a7-133">總數的目前狀態變更次數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-133">Total number of presence change attempts.</span></span> <span data-ttu-id="a51a7-134">對於不同類型的目前狀態變更，請參閱 < SetPresence （目前狀態類型） 的呼叫] 效能計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-134">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-135">NNN 回應的 SetPresence</span><span class="sxs-lookup"><span data-stu-id="a51a7-135">NNN Responses for SetPresence</span></span></p></td>
<td><p><span data-ttu-id="a51a7-136">從伺服器收到 nnn 回應碼的總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-136">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-137">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-137">GetPresence Calls</span></span></p></td>
<td><p><span data-ttu-id="a51a7-138">取得目前狀態要求嘗試的總次數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-138">Total number of get presence request attempts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-139">NNN 回應的 GetPresence</span><span class="sxs-lookup"><span data-stu-id="a51a7-139">NNN Responses for GetPresence</span></span></p></td>
<td><p><span data-ttu-id="a51a7-140">從伺服器收到 nnn 回應碼的總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-140">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-141">**通訊錄服務資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-141">**Address Book service Information**</span></span>

<span data-ttu-id="a51a7-142">此類別包含用來監視下載通訊錄服務 (ABS) 檔案和通訊錄 Web 查詢服務要求的計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-142">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-143"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-143"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-144"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-144"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-145">嘗試 ABS 完整/差異檔案下載</span><span class="sxs-lookup"><span data-stu-id="a51a7-145">ABS Full/Delta File Downloads Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-146">嘗試的完整] 或 [差異檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-146">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-147">ABS 完整/差異檔案下載成功</span><span class="sxs-lookup"><span data-stu-id="a51a7-147">ABS Full/Delta File Downloads Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a51a7-148">嘗試的完整] 或 [差異檔案下載要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-148">Total number of full or delta file download requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-149">通訊錄 Web 查詢服務相關計數器</span><span class="sxs-lookup"><span data-stu-id="a51a7-149">Address Book Web Query service related counters</span></span></p></td>
<td><p><span data-ttu-id="a51a7-150">通訊錄檔案下載相關的計數器。</span><span class="sxs-lookup"><span data-stu-id="a51a7-150">Address book file download related counters.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-151">嘗試 ABS WS 通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-151">ABS WS Calls attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-152">嘗試的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-152">Total number of Address Book Web Query service requests attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-153">ABS WS 通話成功</span><span class="sxs-lookup"><span data-stu-id="a51a7-153">ABS WS Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a51a7-154">傳回成功回應程式碼的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-154">Total number of Address Book Web Query service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-155">ABS WS 通話失敗</span><span class="sxs-lookup"><span data-stu-id="a51a7-155">ABS WS Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a51a7-156">傳回的錯誤回應程式碼的通訊錄 Web 查詢服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-156">Total number of Address Book Web Query service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-157">**通訊清單 (DL) 的資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-157">**Distribution List (DL) Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-158"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-158"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-159"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-159"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-160">嘗試的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-160">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-161">通訊群組清單擴充 (DLX) web 服務要求嘗試總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-161">Total number of distribution list expansion (DLX) web service requests attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-162">成功的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-162">Calls Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a51a7-163">傳回成功回應程式碼的 DLX web 服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-163">Total number of DLX web service requests that returned a successful response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-164">失敗的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-164">Calls Failed</span></span></p></td>
<td><p><span data-ttu-id="a51a7-165">傳回的錯誤回應程式碼的 DLX web 服務要求總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-165">Total number of DLX web service requests that returned an error response code.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-166">**VoIP Basic 資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-166">**VoIP Basic Information**</span></span>

<span data-ttu-id="a51a7-167">效能計數器下面列出報表號碼所有 voice over IP (VoIP) 通話，包括中繼伺服器的呼叫 / V 會議伺服器、 Edge Server，回應群組應用程式，以及會議自動語音應答，當啟用這些案例。</span><span class="sxs-lookup"><span data-stu-id="a51a7-167">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-168"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-168"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-169"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-169"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-170">呼叫使用中</span><span class="sxs-lookup"><span data-stu-id="a51a7-170">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a51a7-171">總數的傳出連入讀的語音呼叫目前進行中。</span><span class="sxs-lookup"><span data-stu-id="a51a7-171">Total number of incoming/outgoing voice calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-172">終止前所需的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-172">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a51a7-173">已終止的內送/撥出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-173">Total number of incoming/outgoing voice calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-174">拒絕的來電</span><span class="sxs-lookup"><span data-stu-id="a51a7-174">Calls Declined</span></span></p></td>
<td><p><span data-ttu-id="a51a7-175">拒絕的傳入語音呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-175">Total number of incoming voice calls declined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-176">嘗試的傳入/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-176">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-177">嘗試傳入/撥出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-177">Total number of incoming/outgoing voice calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-178">建立內送/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-178">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a51a7-179">建立內送/撥出語音通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-179">Total number of incoming/outgoing voice calls established.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-180">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a51a7-180">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a51a7-181">從伺服器收到 nnn 回應碼的總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-181">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-182">VoIP 複雜率 （%）</span><span class="sxs-lookup"><span data-stu-id="a51a7-182">VoIP Pass Rate (%)</span></span></p></td>
<td><p><span data-ttu-id="a51a7-183">建立/總通話嘗試來電總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-183">Total calls established/Total calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-184">**回應群組服務呼叫的資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-184">**Response Group service Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-185"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-185"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-186"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-186"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-187">呼叫使用中</span><span class="sxs-lookup"><span data-stu-id="a51a7-187">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a51a7-188">回應群組應用程式的作用中呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-188">Total number of active calls to the Response Group application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-189">嘗試的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-189">Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-190">嘗試的通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-190">Total number of calls attempted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-191">**立即訊息 (IM) 通話資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-191">**Instant Messaging (IM) Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-192"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-192"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-193"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-193"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-194">呼叫使用中</span><span class="sxs-lookup"><span data-stu-id="a51a7-194">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a51a7-195">持續傳入/傳出立即訊息的通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-195">Total number of ongoing incoming/outgoing instant messaging calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-196">終止前所需的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-196">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a51a7-197">已終止傳入/傳出立即訊息的來電總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-197">Total number of incoming/outgoing instant messaging calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-198">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a51a7-198">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a51a7-199">從伺服器收到 nnn 回應碼的總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-199">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-200">接收/傳送 IM 訊息</span><span class="sxs-lookup"><span data-stu-id="a51a7-200">IM Messages Received/Sent</span></span></p></td>
<td><p><span data-ttu-id="a51a7-201">訊息總數接收或傳送的所有工作階段。</span><span class="sxs-lookup"><span data-stu-id="a51a7-201">Total number of messages received or sent for all sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-202">嘗試的傳入/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-202">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-203">傳入/傳出立即訊息呼叫嘗試總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-203">Total number of incoming/outgoing instant messaging calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-204">建立內送/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-204">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a51a7-205">建立內送/傳出立即訊息通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-205">Total number of incoming/outgoing instant message calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-206">**應用程式共用通話資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-206">**App Sharing Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-207"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-207"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-208"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-208"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-209">呼叫使用中</span><span class="sxs-lookup"><span data-stu-id="a51a7-209">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a51a7-210">進行中的內送/傳出的應用程式共用通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-210">Total number of ongoing incoming/outgoing application sharing calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-211">終止前所需的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-211">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a51a7-212">總數傳入/傳出的應用程式共用通話已終止。</span><span class="sxs-lookup"><span data-stu-id="a51a7-212">Total number of incoming/outgoing application sharing calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-213">呼叫接收的 NNN</span><span class="sxs-lookup"><span data-stu-id="a51a7-213">Calls Received NNN</span></span></p></td>
<td><p><span data-ttu-id="a51a7-214">從伺服器收到 nnn 回應碼的總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-214">Total number of nnn response codes received from the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-215">嘗試的傳入/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-215">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-216">傳入/傳出的應用程式共用嘗試的通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-216">Total number of incoming/outgoing application sharing calls attempted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-217">建立內送/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-217">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a51a7-218">傳入/傳出的應用程式共用建立的通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-218">Total number of incoming/outgoing application sharing calls established.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-219">**CAA 通話資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-219">**CAA Call Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-220"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-220"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-221"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-221"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-222">呼叫使用中</span><span class="sxs-lookup"><span data-stu-id="a51a7-222">Calls Active</span></span></p></td>
<td><p><span data-ttu-id="a51a7-223">總數傳入/傳出公用交換的電話網路 (PSTN) 通話目前進行中。</span><span class="sxs-lookup"><span data-stu-id="a51a7-223">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-224">終止前所需的通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-224">Calls Terminated</span></span></p></td>
<td><p><span data-ttu-id="a51a7-225">已終止的內送/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-225">Total number of incoming/outgoing PSTN calls already terminated.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-226">嘗試的傳入/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-226">Incoming/Outgoing Calls Attempted</span></span></p></td>
<td><p><span data-ttu-id="a51a7-227">嘗試傳入/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-227">Total number of incoming/outgoing PSTN calls attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-228">建立內送/撥出通話</span><span class="sxs-lookup"><span data-stu-id="a51a7-228">Incoming/Outgoing Calls Established</span></span></p></td>
<td><p><span data-ttu-id="a51a7-229">建立內送/傳出 PSTN 通話總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-229">Total number of incoming/outgoing PSTN calls established.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-230">**會議資訊**</span><span class="sxs-lookup"><span data-stu-id="a51a7-230">**Conference Information**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-231"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-231"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-232"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-232"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-233">作用中的立即訊息會議</span><span class="sxs-lookup"><span data-stu-id="a51a7-233">Active Instant Messaging Conferences</span></span></p></td>
<td><p><span data-ttu-id="a51a7-234">進行中的立即訊息會議總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-234">Total number of ongoing instant messaging conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-235">作用中的音訊/視訊會議</span><span class="sxs-lookup"><span data-stu-id="a51a7-235">Active Audio/Video Conferences</span></span></p></td>
<td><p><span data-ttu-id="a51a7-236">總數的進行中的音訊/視訊 (A / V) 會議。</span><span class="sxs-lookup"><span data-stu-id="a51a7-236">Total number of ongoing audio/video (A/V) conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-237">使用中應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="a51a7-237">Active Application Sharing Conferences</span></span></p></td>
<td><p><span data-ttu-id="a51a7-238">進行中的應用程式共用會議總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-238">Total number of ongoing application sharing conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-239">參與者的數量</span><span class="sxs-lookup"><span data-stu-id="a51a7-239">Number of Participants</span></span></p></td>
<td><p><span data-ttu-id="a51a7-240">目前連線至會議的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-240">Total number of participants currently connected to conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-241">會議排程失敗</span><span class="sxs-lookup"><span data-stu-id="a51a7-241">Conference Schedule Failure</span></span></p></td>
<td><p><span data-ttu-id="a51a7-242">嘗試排程會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-242">Total number of failures while trying to schedule a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-243">加入會議失敗</span><span class="sxs-lookup"><span data-stu-id="a51a7-243">Join Conference Failure</span></span></p></td>
<td><p><span data-ttu-id="a51a7-244">嘗試連線至會議時的失敗總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-244">Total number of failures while trying to connect to a conference.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a51a7-245">**UCWA 用戶端計數器**</span><span class="sxs-lookup"><span data-stu-id="a51a7-245">**UCWA Client Counters**</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a51a7-246"><strong>效能計數器</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-246"><strong>Performance Counter</strong></span></span></th>
<th><span data-ttu-id="a51a7-247"><strong>描述</strong></span><span class="sxs-lookup"><span data-stu-id="a51a7-247"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a51a7-248">總數 IMMCU 聯結成功</span><span class="sxs-lookup"><span data-stu-id="a51a7-248">Total Number of IMMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a51a7-249">加入立即訊息的會議總數。</span><span class="sxs-lookup"><span data-stu-id="a51a7-249">Total number of instant messaging conferences joined.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a51a7-250">總數 DMCU 聯結成功</span><span class="sxs-lookup"><span data-stu-id="a51a7-250">Total Number of DMCU Joins Succeeded</span></span></p></td>
<td><p><span data-ttu-id="a51a7-251">總數的 A / V 會議加入。</span><span class="sxs-lookup"><span data-stu-id="a51a7-251">Total number of A/V conferences joined.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

