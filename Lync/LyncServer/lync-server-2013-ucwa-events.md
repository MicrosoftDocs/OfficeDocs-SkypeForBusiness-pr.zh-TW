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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="03f84-102">在 Lync Server 2013 中 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="03f84-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03f84-103">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="03f84-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="03f84-104">Lync Server 2013 使用整合通訊 Web API （UCWA）來實現多種用途，從存取 Microsoft Exchange 進行連絡人搜尋，以更新行動用戶端的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="03f84-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="03f84-105">UCWA 會將操作行為的記錄寫入為事件種類的資訊、警告和錯誤。</span><span class="sxs-lookup"><span data-stu-id="03f84-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="03f84-106">下表說明可由 UCWA 元件所撰寫的事件。</span><span class="sxs-lookup"><span data-stu-id="03f84-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03f84-107">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="03f84-107">Event ID</span></span></th>
<th><span data-ttu-id="03f84-108">事件種類</span><span class="sxs-lookup"><span data-stu-id="03f84-108">Event Type</span></span></th>
<th><span data-ttu-id="03f84-109">總結</span><span class="sxs-lookup"><span data-stu-id="03f84-109">Summary</span></span></th>
<th><span data-ttu-id="03f84-110">原因與解決方式</span><span class="sxs-lookup"><span data-stu-id="03f84-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03f84-111">20001</span><span class="sxs-lookup"><span data-stu-id="03f84-111">20001</span></span></p></td>
<td><p><span data-ttu-id="03f84-112">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-113">UCWA 初始化</span><span class="sxs-lookup"><span data-stu-id="03f84-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="03f84-114">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-114">N/A</span></span></p>
<p><span data-ttu-id="03f84-115">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-116">20002</span><span class="sxs-lookup"><span data-stu-id="03f84-116">20002</span></span></p></td>
<td><p><span data-ttu-id="03f84-117">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-117">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-118">UCWA 在初始化期間遇到意外的例外狀況</span><span class="sxs-lookup"><span data-stu-id="03f84-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="03f84-119">初始化時發生意外的錯誤</span><span class="sxs-lookup"><span data-stu-id="03f84-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="03f84-120">檢查相關聯的事件記錄條目中的例外詳細資料，以判斷可能的原因</span><span class="sxs-lookup"><span data-stu-id="03f84-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-121">20003</span><span class="sxs-lookup"><span data-stu-id="03f84-121">20003</span></span></p></td>
<td><p><span data-ttu-id="03f84-122">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-122">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-123">UCWA 遇到未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="03f84-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="03f84-124">發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="03f84-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="03f84-125">重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="03f84-125">Restart the server.</span></span> <span data-ttu-id="03f84-126">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="03f84-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-127">20004</span><span class="sxs-lookup"><span data-stu-id="03f84-127">20004</span></span></p></td>
<td><p><span data-ttu-id="03f84-128">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-128">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-129">無法存取 HD 相片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="03f84-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="03f84-130">無法連線到 Exchange</span><span class="sxs-lookup"><span data-stu-id="03f84-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="03f84-131">確認已提供與 Exchange 的連線</span><span class="sxs-lookup"><span data-stu-id="03f84-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-132">20005</span><span class="sxs-lookup"><span data-stu-id="03f84-132">20005</span></span></p></td>
<td><p><span data-ttu-id="03f84-133">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-134">已從無法存取 HD 相片的 Exchange 復原</span><span class="sxs-lookup"><span data-stu-id="03f84-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="03f84-135">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-136">20006</span><span class="sxs-lookup"><span data-stu-id="03f84-136">20006</span></span></p></td>
<td><p><span data-ttu-id="03f84-137">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-137">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-138">無法存取連絡人搜尋的 Exchange</span><span class="sxs-lookup"><span data-stu-id="03f84-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="03f84-139">無法連線到 Exchange</span><span class="sxs-lookup"><span data-stu-id="03f84-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="03f84-140">確認已提供與 Exchange 的連線</span><span class="sxs-lookup"><span data-stu-id="03f84-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-141">20007</span><span class="sxs-lookup"><span data-stu-id="03f84-141">20007</span></span></p></td>
<td><p><span data-ttu-id="03f84-142">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-143">已從 Exchange 中的搜尋連絡人復原失敗</span><span class="sxs-lookup"><span data-stu-id="03f84-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="03f84-144">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-145">20008</span><span class="sxs-lookup"><span data-stu-id="03f84-145">20008</span></span></p></td>
<td><p><span data-ttu-id="03f84-146">警告</span><span class="sxs-lookup"><span data-stu-id="03f84-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="03f84-147">嘗試訂閱超過每個應用程式允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="03f84-148">嘗試訂閱超過每個應用程式允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="03f84-149">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-150">20009</span><span class="sxs-lookup"><span data-stu-id="03f84-150">20009</span></span></p></td>
<td><p><span data-ttu-id="03f84-151">警告</span><span class="sxs-lookup"><span data-stu-id="03f84-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="03f84-152">每批次嘗試訂閱超過允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="03f84-153">每批次嘗試訂閱超過允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="03f84-154">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="03f84-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-155">20010</span><span class="sxs-lookup"><span data-stu-id="03f84-155">20010</span></span></p></td>
<td><p><span data-ttu-id="03f84-156">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-156">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-157">無法檢索 inband 資料</span><span class="sxs-lookup"><span data-stu-id="03f84-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="03f84-158">無法檢索 inband 資料</span><span class="sxs-lookup"><span data-stu-id="03f84-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="03f84-159">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="03f84-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-160">20011</span><span class="sxs-lookup"><span data-stu-id="03f84-160">20011</span></span></p></td>
<td><p><span data-ttu-id="03f84-161">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-161">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-162">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="03f84-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="03f84-163">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="03f84-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="03f84-164">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="03f84-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-165">20012</span><span class="sxs-lookup"><span data-stu-id="03f84-165">20012</span></span></p></td>
<td><p><span data-ttu-id="03f84-166">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-166">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-167">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="03f84-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="03f84-168">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="03f84-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="03f84-169">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="03f84-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-170">20013</span><span class="sxs-lookup"><span data-stu-id="03f84-170">20013</span></span></p></td>
<td><p><span data-ttu-id="03f84-171">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-171">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-172">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="03f84-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="03f84-173">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="03f84-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="03f84-174">查看 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-175">20014</span><span class="sxs-lookup"><span data-stu-id="03f84-175">20014</span></span></p></td>
<td><p><span data-ttu-id="03f84-176">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-177">已從無法連線至 IM MCU 的故障復原</span><span class="sxs-lookup"><span data-stu-id="03f84-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-178">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-179">20015</span><span class="sxs-lookup"><span data-stu-id="03f84-179">20015</span></span></p></td>
<td><p><span data-ttu-id="03f84-180">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-180">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-181">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="03f84-182">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="03f84-183">查看 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-184">20016</span><span class="sxs-lookup"><span data-stu-id="03f84-184">20016</span></span></p></td>
<td><p><span data-ttu-id="03f84-185">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-186">從無法連線到 AV MCU 的故障復原</span><span class="sxs-lookup"><span data-stu-id="03f84-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-187">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-188">20017</span><span class="sxs-lookup"><span data-stu-id="03f84-188">20017</span></span></p></td>
<td><p><span data-ttu-id="03f84-189">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-189">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-190">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="03f84-191">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="03f84-192">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-193">20018</span><span class="sxs-lookup"><span data-stu-id="03f84-193">20018</span></span></p></td>
<td><p><span data-ttu-id="03f84-194">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-195">從無法連線到 MCU 的方式復原</span><span class="sxs-lookup"><span data-stu-id="03f84-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-196">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-197">20019</span><span class="sxs-lookup"><span data-stu-id="03f84-197">20019</span></span></p></td>
<td><p><span data-ttu-id="03f84-198">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-198">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-199">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="03f84-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="03f84-200">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="03f84-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="03f84-201">查看資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-202">20020</span><span class="sxs-lookup"><span data-stu-id="03f84-202">20020</span></span></p></td>
<td><p><span data-ttu-id="03f84-203">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-204">從無法連線到資料 MCU 的情況中復原</span><span class="sxs-lookup"><span data-stu-id="03f84-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-205">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-206">20021</span><span class="sxs-lookup"><span data-stu-id="03f84-206">20021</span></span></p></td>
<td><p><span data-ttu-id="03f84-207">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-207">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-208">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-209">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="03f84-210">查看 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-211">20022</span><span class="sxs-lookup"><span data-stu-id="03f84-211">20022</span></span></p></td>
<td><p><span data-ttu-id="03f84-212">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-212">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-213">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-214">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="03f84-215">查看 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-216">20023</span><span class="sxs-lookup"><span data-stu-id="03f84-216">20023</span></span></p></td>
<td><p><span data-ttu-id="03f84-217">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-217">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-218">無法以 MCU 進行加入</span><span class="sxs-lookup"><span data-stu-id="03f84-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-219">無法以 MCU 進行加入</span><span class="sxs-lookup"><span data-stu-id="03f84-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="03f84-220">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-221">20024</span><span class="sxs-lookup"><span data-stu-id="03f84-221">20024</span></span></p></td>
<td><p><span data-ttu-id="03f84-222">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-222">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-223">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="03f84-224">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="03f84-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="03f84-225">查看資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="03f84-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-226">20025</span><span class="sxs-lookup"><span data-stu-id="03f84-226">20025</span></span></p></td>
<td><p><span data-ttu-id="03f84-227">出錯</span><span class="sxs-lookup"><span data-stu-id="03f84-227">Error</span></span></p></td>
<td><p><span data-ttu-id="03f84-228">無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="03f84-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="03f84-229">無法使用 active directory 連線</span><span class="sxs-lookup"><span data-stu-id="03f84-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="03f84-230">確定有可用的連線至 active directory</span><span class="sxs-lookup"><span data-stu-id="03f84-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03f84-231">20026</span><span class="sxs-lookup"><span data-stu-id="03f84-231">20026</span></span></p></td>
<td><p><span data-ttu-id="03f84-232">參考</span><span class="sxs-lookup"><span data-stu-id="03f84-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="03f84-233">已復原無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="03f84-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="03f84-234">不適用</span><span class="sxs-lookup"><span data-stu-id="03f84-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03f84-235">20027</span><span class="sxs-lookup"><span data-stu-id="03f84-235">20027</span></span></p></td>
<td><p><span data-ttu-id="03f84-236">警告</span><span class="sxs-lookup"><span data-stu-id="03f84-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="03f84-237">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="03f84-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="03f84-238">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="03f84-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="03f84-239">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="03f84-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

