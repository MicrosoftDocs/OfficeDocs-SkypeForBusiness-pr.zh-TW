---
title: Lync Server 2013： UCWA 事件
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
ms.openlocfilehash: 1ae71fa6e91c0bc212bc019b1afa85ebcacb4d0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527790"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="e48eb-102">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="e48eb-102">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e48eb-103">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="e48eb-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="e48eb-104">Lync Server 2013 使用整合通訊 Web API (UCWA) 出於許多目的，從存取 Microsoft Exchange 以進行連絡人搜尋，以更新行動用戶端的狀態。</span><span class="sxs-lookup"><span data-stu-id="e48eb-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="e48eb-105">UCWA 會將操作行為記錄撰寫成事件種類的資訊、警告和錯誤。</span><span class="sxs-lookup"><span data-stu-id="e48eb-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="e48eb-106">下表說明 UCWA 元件可寫入的事件。</span><span class="sxs-lookup"><span data-stu-id="e48eb-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e48eb-107">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="e48eb-107">Event ID</span></span></th>
<th><span data-ttu-id="e48eb-108">事件類型</span><span class="sxs-lookup"><span data-stu-id="e48eb-108">Event Type</span></span></th>
<th><span data-ttu-id="e48eb-109">摘要</span><span class="sxs-lookup"><span data-stu-id="e48eb-109">Summary</span></span></th>
<th><span data-ttu-id="e48eb-110">原因和解決方法</span><span class="sxs-lookup"><span data-stu-id="e48eb-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-111">20001</span><span class="sxs-lookup"><span data-stu-id="e48eb-111">20001</span></span></p></td>
<td><p><span data-ttu-id="e48eb-112">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-113">UCWA 初始化</span><span class="sxs-lookup"><span data-stu-id="e48eb-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="e48eb-114">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-114">N/A</span></span></p>
<p><span data-ttu-id="e48eb-115">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-116">20002</span><span class="sxs-lookup"><span data-stu-id="e48eb-116">20002</span></span></p></td>
<td><p><span data-ttu-id="e48eb-117">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-117">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-118">UCWA 在初始化期間遇到意外的例外狀況</span><span class="sxs-lookup"><span data-stu-id="e48eb-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="e48eb-119">初始化時發生未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="e48eb-120">檢查相關事件記錄檔專案中的例外狀況詳細資料，以判斷可能的原因</span><span class="sxs-lookup"><span data-stu-id="e48eb-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-121">20003</span><span class="sxs-lookup"><span data-stu-id="e48eb-121">20003</span></span></p></td>
<td><p><span data-ttu-id="e48eb-122">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-122">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-123">UCWA 發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="e48eb-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="e48eb-124">發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="e48eb-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="e48eb-125">重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="e48eb-125">Restart the server.</span></span> <span data-ttu-id="e48eb-126">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="e48eb-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-127">20004</span><span class="sxs-lookup"><span data-stu-id="e48eb-127">20004</span></span></p></td>
<td><p><span data-ttu-id="e48eb-128">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-128">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-129">無法存取 HD 相片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="e48eb-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="e48eb-130">無法使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="e48eb-131">確定可使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-132">20005</span><span class="sxs-lookup"><span data-stu-id="e48eb-132">20005</span></span></p></td>
<td><p><span data-ttu-id="e48eb-133">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-134">從無法存取 HD 相片的 Exchange 復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="e48eb-135">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-136">20006</span><span class="sxs-lookup"><span data-stu-id="e48eb-136">20006</span></span></p></td>
<td><p><span data-ttu-id="e48eb-137">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-137">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-138">無法存取連絡人搜尋的 Exchange</span><span class="sxs-lookup"><span data-stu-id="e48eb-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="e48eb-139">無法使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="e48eb-140">確定可使用 Exchange 連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-141">20007</span><span class="sxs-lookup"><span data-stu-id="e48eb-141">20007</span></span></p></td>
<td><p><span data-ttu-id="e48eb-142">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-143">從 Exchange 中的搜尋連絡人復原失敗</span><span class="sxs-lookup"><span data-stu-id="e48eb-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="e48eb-144">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-145">20008</span><span class="sxs-lookup"><span data-stu-id="e48eb-145">20008</span></span></p></td>
<td><p><span data-ttu-id="e48eb-146">警告</span><span class="sxs-lookup"><span data-stu-id="e48eb-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="e48eb-147">嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="e48eb-148">嘗試訂閱超過每個應用程式允許的顯示狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="e48eb-149">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-150">20009</span><span class="sxs-lookup"><span data-stu-id="e48eb-150">20009</span></span></p></td>
<td><p><span data-ttu-id="e48eb-151">警告</span><span class="sxs-lookup"><span data-stu-id="e48eb-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="e48eb-152">嘗試訂閱每批次允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="e48eb-153">嘗試訂閱每批次允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="e48eb-154">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="e48eb-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-155">20010</span><span class="sxs-lookup"><span data-stu-id="e48eb-155">20010</span></span></p></td>
<td><p><span data-ttu-id="e48eb-156">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-156">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-157">無法取得 inband 資料</span><span class="sxs-lookup"><span data-stu-id="e48eb-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="e48eb-158">無法取得 inband 資料</span><span class="sxs-lookup"><span data-stu-id="e48eb-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="e48eb-159">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="e48eb-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-160">20011</span><span class="sxs-lookup"><span data-stu-id="e48eb-160">20011</span></span></p></td>
<td><p><span data-ttu-id="e48eb-161">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-161">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-162">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="e48eb-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="e48eb-163">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="e48eb-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="e48eb-164">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="e48eb-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-165">20012</span><span class="sxs-lookup"><span data-stu-id="e48eb-165">20012</span></span></p></td>
<td><p><span data-ttu-id="e48eb-166">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-166">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-167">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="e48eb-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="e48eb-168">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="e48eb-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="e48eb-169">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="e48eb-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-170">20013</span><span class="sxs-lookup"><span data-stu-id="e48eb-170">20013</span></span></p></td>
<td><p><span data-ttu-id="e48eb-171">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-171">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-172">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="e48eb-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e48eb-173">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="e48eb-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="e48eb-174">查看 IM MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-175">20014</span><span class="sxs-lookup"><span data-stu-id="e48eb-175">20014</span></span></p></td>
<td><p><span data-ttu-id="e48eb-176">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-177">從無法連線至 IM MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-178">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-179">20015</span><span class="sxs-lookup"><span data-stu-id="e48eb-179">20015</span></span></p></td>
<td><p><span data-ttu-id="e48eb-180">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-180">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-181">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e48eb-182">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="e48eb-183">查看 AV MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-184">20016</span><span class="sxs-lookup"><span data-stu-id="e48eb-184">20016</span></span></p></td>
<td><p><span data-ttu-id="e48eb-185">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-186">從無法連線至 AV MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-187">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-188">20017</span><span class="sxs-lookup"><span data-stu-id="e48eb-188">20017</span></span></p></td>
<td><p><span data-ttu-id="e48eb-189">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-189">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-190">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e48eb-191">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="e48eb-192">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-193">20018</span><span class="sxs-lookup"><span data-stu-id="e48eb-193">20018</span></span></p></td>
<td><p><span data-ttu-id="e48eb-194">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-195">從無法以 MCU 形式連線的方式復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-196">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-197">20019</span><span class="sxs-lookup"><span data-stu-id="e48eb-197">20019</span></span></p></td>
<td><p><span data-ttu-id="e48eb-198">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-198">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-199">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="e48eb-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e48eb-200">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="e48eb-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="e48eb-201">查看資料 MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-202">20020</span><span class="sxs-lookup"><span data-stu-id="e48eb-202">20020</span></span></p></td>
<td><p><span data-ttu-id="e48eb-203">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-204">從無法連線至資料 MCU 的失敗復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-205">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-206">20021</span><span class="sxs-lookup"><span data-stu-id="e48eb-206">20021</span></span></p></td>
<td><p><span data-ttu-id="e48eb-207">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-207">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-208">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-209">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="e48eb-210">查看 IM MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-211">20022</span><span class="sxs-lookup"><span data-stu-id="e48eb-211">20022</span></span></p></td>
<td><p><span data-ttu-id="e48eb-212">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-212">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-213">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-214">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="e48eb-215">查看 AV MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-216">20023</span><span class="sxs-lookup"><span data-stu-id="e48eb-216">20023</span></span></p></td>
<td><p><span data-ttu-id="e48eb-217">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-217">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-218">無法以 MCU 形式加入</span><span class="sxs-lookup"><span data-stu-id="e48eb-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-219">無法以 MCU 形式加入</span><span class="sxs-lookup"><span data-stu-id="e48eb-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="e48eb-220">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-221">20024</span><span class="sxs-lookup"><span data-stu-id="e48eb-221">20024</span></span></p></td>
<td><p><span data-ttu-id="e48eb-222">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-222">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-223">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="e48eb-224">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="e48eb-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="e48eb-225">查看資料 MCU 是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="e48eb-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-226">20025</span><span class="sxs-lookup"><span data-stu-id="e48eb-226">20025</span></span></p></td>
<td><p><span data-ttu-id="e48eb-227">錯誤</span><span class="sxs-lookup"><span data-stu-id="e48eb-227">Error</span></span></p></td>
<td><p><span data-ttu-id="e48eb-228">無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="e48eb-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="e48eb-229">無法使用 active directory 的連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="e48eb-230">確定可以使用 active directory 的連線</span><span class="sxs-lookup"><span data-stu-id="e48eb-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48eb-231">20026</span><span class="sxs-lookup"><span data-stu-id="e48eb-231">20026</span></span></p></td>
<td><p><span data-ttu-id="e48eb-232">資訊</span><span class="sxs-lookup"><span data-stu-id="e48eb-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="e48eb-233">從無法存取相片的 active directory 復原</span><span class="sxs-lookup"><span data-stu-id="e48eb-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="e48eb-234">不適用</span><span class="sxs-lookup"><span data-stu-id="e48eb-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48eb-235">20027</span><span class="sxs-lookup"><span data-stu-id="e48eb-235">20027</span></span></p></td>
<td><p><span data-ttu-id="e48eb-236">警告</span><span class="sxs-lookup"><span data-stu-id="e48eb-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="e48eb-237">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="e48eb-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="e48eb-238">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="e48eb-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="e48eb-239">如果問題仍然存在，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="e48eb-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

