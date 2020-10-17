---
title: Lync Server 2013： UCWA 事件
description: Lync Server 2013： UCWA 事件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548849"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="177e9-103">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="177e9-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="177e9-104">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="177e9-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="177e9-105">Lync Server 2013 使用整合通訊 Web API (UCWA) 出於許多目的，從存取 Microsoft Exchange 以進行連絡人搜尋，以更新行動用戶端的狀態。</span><span class="sxs-lookup"><span data-stu-id="177e9-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="177e9-106">UCWA 會將操作行為記錄撰寫成事件種類的資訊、警告和錯誤。</span><span class="sxs-lookup"><span data-stu-id="177e9-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="177e9-107">下表說明 UCWA 元件可寫入的事件。</span><span class="sxs-lookup"><span data-stu-id="177e9-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="177e9-108">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="177e9-108">Event ID</span></span></th>
<th><span data-ttu-id="177e9-109">事件類型</span><span class="sxs-lookup"><span data-stu-id="177e9-109">Event Type</span></span></th>
<th><span data-ttu-id="177e9-110">摘要</span><span class="sxs-lookup"><span data-stu-id="177e9-110">Summary</span></span></th>
<th><span data-ttu-id="177e9-111">原因和解決方法</span><span class="sxs-lookup"><span data-stu-id="177e9-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="177e9-112">20001</span><span class="sxs-lookup"><span data-stu-id="177e9-112">20001</span></span></p></td>
<td><p><span data-ttu-id="177e9-113">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-114">UCWA 初始化</span><span class="sxs-lookup"><span data-stu-id="177e9-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="177e9-115">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-115">N/A</span></span></p>
<p><span data-ttu-id="177e9-116">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-117">20002</span><span class="sxs-lookup"><span data-stu-id="177e9-117">20002</span></span></p></td>
<td><p><span data-ttu-id="177e9-118">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-118">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-119">UCWA 在初始化期間遇到意外的例外狀況</span><span class="sxs-lookup"><span data-stu-id="177e9-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="177e9-120">初始化時發生未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="177e9-121">檢查相關事件記錄檔專案中的例外狀況詳細資料，以判斷可能的原因</span><span class="sxs-lookup"><span data-stu-id="177e9-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-122">20003</span><span class="sxs-lookup"><span data-stu-id="177e9-122">20003</span></span></p></td>
<td><p><span data-ttu-id="177e9-123">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-123">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-124">UCWA 發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="177e9-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="177e9-125">發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="177e9-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="177e9-126">重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="177e9-126">Restart the server.</span></span> <span data-ttu-id="177e9-127">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="177e9-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-128">20004</span><span class="sxs-lookup"><span data-stu-id="177e9-128">20004</span></span></p></td>
<td><p><span data-ttu-id="177e9-129">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-129">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-130">無法存取 HD 相片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="177e9-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="177e9-131">無法使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="177e9-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="177e9-132">確定可使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="177e9-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-133">20005</span><span class="sxs-lookup"><span data-stu-id="177e9-133">20005</span></span></p></td>
<td><p><span data-ttu-id="177e9-134">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-135">從無法存取 HD 相片的 Exchange 復原</span><span class="sxs-lookup"><span data-stu-id="177e9-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="177e9-136">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-137">20006</span><span class="sxs-lookup"><span data-stu-id="177e9-137">20006</span></span></p></td>
<td><p><span data-ttu-id="177e9-138">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-138">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-139">無法存取連絡人搜尋的 Exchange</span><span class="sxs-lookup"><span data-stu-id="177e9-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="177e9-140">無法使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="177e9-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="177e9-141">確定可使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="177e9-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-142">20007</span><span class="sxs-lookup"><span data-stu-id="177e9-142">20007</span></span></p></td>
<td><p><span data-ttu-id="177e9-143">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-144">從 Exchange 中的搜尋連絡人復原失敗</span><span class="sxs-lookup"><span data-stu-id="177e9-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="177e9-145">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-146">20008</span><span class="sxs-lookup"><span data-stu-id="177e9-146">20008</span></span></p></td>
<td><p><span data-ttu-id="177e9-147">警告</span><span class="sxs-lookup"><span data-stu-id="177e9-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="177e9-148">嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="177e9-149">嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="177e9-150">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-151">20009</span><span class="sxs-lookup"><span data-stu-id="177e9-151">20009</span></span></p></td>
<td><p><span data-ttu-id="177e9-152">警告</span><span class="sxs-lookup"><span data-stu-id="177e9-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="177e9-153">嘗試訂閱每批次允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="177e9-154">嘗試訂閱每批次允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="177e9-155">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="177e9-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-156">20010</span><span class="sxs-lookup"><span data-stu-id="177e9-156">20010</span></span></p></td>
<td><p><span data-ttu-id="177e9-157">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-157">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-158">無法取得 inband 資料</span><span class="sxs-lookup"><span data-stu-id="177e9-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="177e9-159">無法取得 inband 資料</span><span class="sxs-lookup"><span data-stu-id="177e9-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="177e9-160">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="177e9-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-161">20011</span><span class="sxs-lookup"><span data-stu-id="177e9-161">20011</span></span></p></td>
<td><p><span data-ttu-id="177e9-162">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-162">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-163">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="177e9-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="177e9-164">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="177e9-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="177e9-165">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="177e9-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-166">20012</span><span class="sxs-lookup"><span data-stu-id="177e9-166">20012</span></span></p></td>
<td><p><span data-ttu-id="177e9-167">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-167">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-168">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="177e9-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="177e9-169">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="177e9-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="177e9-170">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="177e9-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-171">20013</span><span class="sxs-lookup"><span data-stu-id="177e9-171">20013</span></span></p></td>
<td><p><span data-ttu-id="177e9-172">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-172">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-173">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="177e9-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="177e9-174">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="177e9-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="177e9-175">查看 IM MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-176">20014</span><span class="sxs-lookup"><span data-stu-id="177e9-176">20014</span></span></p></td>
<td><p><span data-ttu-id="177e9-177">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-178">從無法連線至 IM MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="177e9-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-179">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-180">20015</span><span class="sxs-lookup"><span data-stu-id="177e9-180">20015</span></span></p></td>
<td><p><span data-ttu-id="177e9-181">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-181">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-182">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="177e9-183">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="177e9-184">查看 AV MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-185">20016</span><span class="sxs-lookup"><span data-stu-id="177e9-185">20016</span></span></p></td>
<td><p><span data-ttu-id="177e9-186">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-187">從無法連線至 AV MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="177e9-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-188">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-189">20017</span><span class="sxs-lookup"><span data-stu-id="177e9-189">20017</span></span></p></td>
<td><p><span data-ttu-id="177e9-190">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-190">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-191">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="177e9-192">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="177e9-193">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-194">20018</span><span class="sxs-lookup"><span data-stu-id="177e9-194">20018</span></span></p></td>
<td><p><span data-ttu-id="177e9-195">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-196">從無法以 MCU 形式連線的方式復原</span><span class="sxs-lookup"><span data-stu-id="177e9-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-197">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-198">20019</span><span class="sxs-lookup"><span data-stu-id="177e9-198">20019</span></span></p></td>
<td><p><span data-ttu-id="177e9-199">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-199">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-200">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="177e9-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="177e9-201">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="177e9-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="177e9-202">查看資料 MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-203">20020</span><span class="sxs-lookup"><span data-stu-id="177e9-203">20020</span></span></p></td>
<td><p><span data-ttu-id="177e9-204">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-205">從無法連線至資料 MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="177e9-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-206">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-207">20021</span><span class="sxs-lookup"><span data-stu-id="177e9-207">20021</span></span></p></td>
<td><p><span data-ttu-id="177e9-208">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-208">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-209">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-210">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="177e9-211">查看 IM MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-212">20022</span><span class="sxs-lookup"><span data-stu-id="177e9-212">20022</span></span></p></td>
<td><p><span data-ttu-id="177e9-213">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-213">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-214">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-215">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="177e9-216">查看 AV MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-217">20023</span><span class="sxs-lookup"><span data-stu-id="177e9-217">20023</span></span></p></td>
<td><p><span data-ttu-id="177e9-218">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-218">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-219">無法以 MCU 形式加入</span><span class="sxs-lookup"><span data-stu-id="177e9-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-220">無法以 MCU 形式加入</span><span class="sxs-lookup"><span data-stu-id="177e9-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="177e9-221">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-222">20024</span><span class="sxs-lookup"><span data-stu-id="177e9-222">20024</span></span></p></td>
<td><p><span data-ttu-id="177e9-223">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-223">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-224">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="177e9-225">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="177e9-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="177e9-226">查看資料 MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="177e9-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-227">20025</span><span class="sxs-lookup"><span data-stu-id="177e9-227">20025</span></span></p></td>
<td><p><span data-ttu-id="177e9-228">錯誤</span><span class="sxs-lookup"><span data-stu-id="177e9-228">Error</span></span></p></td>
<td><p><span data-ttu-id="177e9-229">無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="177e9-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="177e9-230">無法使用 active directory 的連線</span><span class="sxs-lookup"><span data-stu-id="177e9-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="177e9-231">確定可以使用 active directory 的連線</span><span class="sxs-lookup"><span data-stu-id="177e9-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177e9-232">20026</span><span class="sxs-lookup"><span data-stu-id="177e9-232">20026</span></span></p></td>
<td><p><span data-ttu-id="177e9-233">資訊</span><span class="sxs-lookup"><span data-stu-id="177e9-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="177e9-234">從無法存取相片的 active directory 復原</span><span class="sxs-lookup"><span data-stu-id="177e9-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="177e9-235">不適用</span><span class="sxs-lookup"><span data-stu-id="177e9-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177e9-236">20027</span><span class="sxs-lookup"><span data-stu-id="177e9-236">20027</span></span></p></td>
<td><p><span data-ttu-id="177e9-237">警告</span><span class="sxs-lookup"><span data-stu-id="177e9-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="177e9-238">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="177e9-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="177e9-239">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="177e9-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="177e9-240">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="177e9-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

