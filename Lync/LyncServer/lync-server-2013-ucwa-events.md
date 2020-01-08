---
title: Lync Server 2013： UCWA 事件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="33213-102">在 Lync Server 2013 中 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="33213-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33213-103">_**主題上次修改日期：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="33213-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="33213-104">Lync Server 2013 使用整合通訊 Web API （UCWA）來實現多種用途，從存取 Microsoft Exchange 進行連絡人搜尋，以更新行動用戶端的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="33213-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="33213-105">UCWA 會將操作行為的記錄寫入為事件種類的資訊、警告和錯誤。</span><span class="sxs-lookup"><span data-stu-id="33213-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="33213-106">下表說明可由 UCWA 元件所撰寫的事件。</span><span class="sxs-lookup"><span data-stu-id="33213-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33213-107">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="33213-107">Event ID</span></span></th>
<th><span data-ttu-id="33213-108">事件種類</span><span class="sxs-lookup"><span data-stu-id="33213-108">Event Type</span></span></th>
<th><span data-ttu-id="33213-109">總結</span><span class="sxs-lookup"><span data-stu-id="33213-109">Summary</span></span></th>
<th><span data-ttu-id="33213-110">原因與解決方式</span><span class="sxs-lookup"><span data-stu-id="33213-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33213-111">20001</span><span class="sxs-lookup"><span data-stu-id="33213-111">20001</span></span></p></td>
<td><p><span data-ttu-id="33213-112">參考</span><span class="sxs-lookup"><span data-stu-id="33213-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-113">UCWA 初始化</span><span class="sxs-lookup"><span data-stu-id="33213-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="33213-114">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-114">N/A</span></span></p>
<p><span data-ttu-id="33213-115">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-116">20002</span><span class="sxs-lookup"><span data-stu-id="33213-116">20002</span></span></p></td>
<td><p><span data-ttu-id="33213-117">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-117">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-118">UCWA 在初始化期間遇到意外的例外狀況</span><span class="sxs-lookup"><span data-stu-id="33213-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="33213-119">初始化時發生意外的錯誤</span><span class="sxs-lookup"><span data-stu-id="33213-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="33213-120">檢查相關聯的事件記錄條目中的例外詳細資料，以判斷可能的原因</span><span class="sxs-lookup"><span data-stu-id="33213-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-121">20003</span><span class="sxs-lookup"><span data-stu-id="33213-121">20003</span></span></p></td>
<td><p><span data-ttu-id="33213-122">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-122">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-123">UCWA 遇到未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="33213-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="33213-124">發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="33213-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="33213-125">重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="33213-125">Restart the server.</span></span> <span data-ttu-id="33213-126">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="33213-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-127">20004</span><span class="sxs-lookup"><span data-stu-id="33213-127">20004</span></span></p></td>
<td><p><span data-ttu-id="33213-128">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-128">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-129">無法存取 HD 相片的 Exchange</span><span class="sxs-lookup"><span data-stu-id="33213-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="33213-130">無法連線到 Exchange</span><span class="sxs-lookup"><span data-stu-id="33213-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="33213-131">確認已提供與 Exchange 的連線</span><span class="sxs-lookup"><span data-stu-id="33213-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-132">20005</span><span class="sxs-lookup"><span data-stu-id="33213-132">20005</span></span></p></td>
<td><p><span data-ttu-id="33213-133">參考</span><span class="sxs-lookup"><span data-stu-id="33213-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-134">已從無法存取 HD 相片的 Exchange 復原</span><span class="sxs-lookup"><span data-stu-id="33213-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="33213-135">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-136">20006</span><span class="sxs-lookup"><span data-stu-id="33213-136">20006</span></span></p></td>
<td><p><span data-ttu-id="33213-137">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-137">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-138">無法存取連絡人搜尋的 Exchange</span><span class="sxs-lookup"><span data-stu-id="33213-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="33213-139">無法連線到 Exchange</span><span class="sxs-lookup"><span data-stu-id="33213-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="33213-140">確認已提供與 Exchange 的連線</span><span class="sxs-lookup"><span data-stu-id="33213-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-141">20007</span><span class="sxs-lookup"><span data-stu-id="33213-141">20007</span></span></p></td>
<td><p><span data-ttu-id="33213-142">參考</span><span class="sxs-lookup"><span data-stu-id="33213-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-143">已從 Exchange 中的搜尋連絡人復原失敗</span><span class="sxs-lookup"><span data-stu-id="33213-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="33213-144">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-145">20008</span><span class="sxs-lookup"><span data-stu-id="33213-145">20008</span></span></p></td>
<td><p><span data-ttu-id="33213-146">警告</span><span class="sxs-lookup"><span data-stu-id="33213-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="33213-147">嘗試訂閱超過每個應用程式允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="33213-148">嘗試訂閱超過每個應用程式允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="33213-149">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-150">20009</span><span class="sxs-lookup"><span data-stu-id="33213-150">20009</span></span></p></td>
<td><p><span data-ttu-id="33213-151">警告</span><span class="sxs-lookup"><span data-stu-id="33213-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="33213-152">每批次嘗試訂閱超過允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="33213-153">每批次嘗試訂閱超過允許的目前狀態訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="33213-154">檢查用戶端是否有不必要的訂閱</span><span class="sxs-lookup"><span data-stu-id="33213-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-155">20010</span><span class="sxs-lookup"><span data-stu-id="33213-155">20010</span></span></p></td>
<td><p><span data-ttu-id="33213-156">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-156">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-157">無法檢索 inband 資料</span><span class="sxs-lookup"><span data-stu-id="33213-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="33213-158">無法檢索 inband 資料</span><span class="sxs-lookup"><span data-stu-id="33213-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="33213-159">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="33213-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-160">20011</span><span class="sxs-lookup"><span data-stu-id="33213-160">20011</span></span></p></td>
<td><p><span data-ttu-id="33213-161">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-161">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-162">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="33213-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="33213-163">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="33213-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="33213-164">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="33213-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-165">20012</span><span class="sxs-lookup"><span data-stu-id="33213-165">20012</span></span></p></td>
<td><p><span data-ttu-id="33213-166">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-166">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-167">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="33213-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="33213-168">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="33213-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="33213-169">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="33213-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-170">20013</span><span class="sxs-lookup"><span data-stu-id="33213-170">20013</span></span></p></td>
<td><p><span data-ttu-id="33213-171">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-171">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-172">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="33213-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="33213-173">IM MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="33213-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="33213-174">查看 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-175">20014</span><span class="sxs-lookup"><span data-stu-id="33213-175">20014</span></span></p></td>
<td><p><span data-ttu-id="33213-176">參考</span><span class="sxs-lookup"><span data-stu-id="33213-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-177">已從無法連線至 IM MCU 的故障復原</span><span class="sxs-lookup"><span data-stu-id="33213-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-178">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-179">20015</span><span class="sxs-lookup"><span data-stu-id="33213-179">20015</span></span></p></td>
<td><p><span data-ttu-id="33213-180">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-180">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-181">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="33213-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="33213-182">無法使用 AV MCU</span><span class="sxs-lookup"><span data-stu-id="33213-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="33213-183">查看 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-184">20016</span><span class="sxs-lookup"><span data-stu-id="33213-184">20016</span></span></p></td>
<td><p><span data-ttu-id="33213-185">參考</span><span class="sxs-lookup"><span data-stu-id="33213-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-186">從無法連線到 AV MCU 的故障復原</span><span class="sxs-lookup"><span data-stu-id="33213-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-187">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-188">20017</span><span class="sxs-lookup"><span data-stu-id="33213-188">20017</span></span></p></td>
<td><p><span data-ttu-id="33213-189">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-189">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-190">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="33213-191">無法使用 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="33213-192">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-193">20018</span><span class="sxs-lookup"><span data-stu-id="33213-193">20018</span></span></p></td>
<td><p><span data-ttu-id="33213-194">參考</span><span class="sxs-lookup"><span data-stu-id="33213-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-195">從無法連線到 MCU 的方式復原</span><span class="sxs-lookup"><span data-stu-id="33213-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-196">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-197">20019</span><span class="sxs-lookup"><span data-stu-id="33213-197">20019</span></span></p></td>
<td><p><span data-ttu-id="33213-198">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-198">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-199">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="33213-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="33213-200">資料 MCU 無法使用</span><span class="sxs-lookup"><span data-stu-id="33213-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="33213-201">查看資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-202">20020</span><span class="sxs-lookup"><span data-stu-id="33213-202">20020</span></span></p></td>
<td><p><span data-ttu-id="33213-203">參考</span><span class="sxs-lookup"><span data-stu-id="33213-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-204">從無法連線到資料 MCU 的情況中復原</span><span class="sxs-lookup"><span data-stu-id="33213-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-205">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-206">20021</span><span class="sxs-lookup"><span data-stu-id="33213-206">20021</span></span></p></td>
<td><p><span data-ttu-id="33213-207">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-207">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-208">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="33213-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-209">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="33213-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="33213-210">查看 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-211">20022</span><span class="sxs-lookup"><span data-stu-id="33213-211">20022</span></span></p></td>
<td><p><span data-ttu-id="33213-212">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-212">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-213">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="33213-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-214">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="33213-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="33213-215">查看 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-216">20023</span><span class="sxs-lookup"><span data-stu-id="33213-216">20023</span></span></p></td>
<td><p><span data-ttu-id="33213-217">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-217">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-218">無法以 MCU 進行加入</span><span class="sxs-lookup"><span data-stu-id="33213-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-219">無法以 MCU 進行加入</span><span class="sxs-lookup"><span data-stu-id="33213-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="33213-220">查看是否正在執行 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-221">20024</span><span class="sxs-lookup"><span data-stu-id="33213-221">20024</span></span></p></td>
<td><p><span data-ttu-id="33213-222">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-222">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-223">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="33213-224">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="33213-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="33213-225">查看資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="33213-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-226">20025</span><span class="sxs-lookup"><span data-stu-id="33213-226">20025</span></span></p></td>
<td><p><span data-ttu-id="33213-227">出錯</span><span class="sxs-lookup"><span data-stu-id="33213-227">Error</span></span></p></td>
<td><p><span data-ttu-id="33213-228">無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="33213-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="33213-229">無法使用 active directory 連線</span><span class="sxs-lookup"><span data-stu-id="33213-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="33213-230">確定有可用的連線至 active directory</span><span class="sxs-lookup"><span data-stu-id="33213-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33213-231">20026</span><span class="sxs-lookup"><span data-stu-id="33213-231">20026</span></span></p></td>
<td><p><span data-ttu-id="33213-232">參考</span><span class="sxs-lookup"><span data-stu-id="33213-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="33213-233">已復原無法存取相片的 active directory</span><span class="sxs-lookup"><span data-stu-id="33213-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="33213-234">不適用</span><span class="sxs-lookup"><span data-stu-id="33213-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33213-235">20027</span><span class="sxs-lookup"><span data-stu-id="33213-235">20027</span></span></p></td>
<td><p><span data-ttu-id="33213-236">警告</span><span class="sxs-lookup"><span data-stu-id="33213-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="33213-237">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="33213-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="33213-238">無法反序列化</span><span class="sxs-lookup"><span data-stu-id="33213-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="33213-239">如果問題持續發生，請與產品支援人員聯繫</span><span class="sxs-lookup"><span data-stu-id="33213-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

