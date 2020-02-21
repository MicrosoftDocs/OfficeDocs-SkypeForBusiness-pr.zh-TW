---
title: 'Lync Server 2013: UCWA 事件'
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
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="4e8a9-102">Lync Server 2013 中的 UCWA 事件</span><span class="sxs-lookup"><span data-stu-id="4e8a9-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e8a9-103">_**上次修改主題：** 2013年-02-15_</span><span class="sxs-lookup"><span data-stu-id="4e8a9-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4e8a9-104">Lync Server 2013 使用數量的目的，以用於行動用戶端更新目前狀態的連絡人搜尋存取 Microsoft Exchange Unified Communications Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="4e8a9-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="4e8a9-105">UCWA 將提示資訊、 警告及錯誤的事件類型為寫入作業行為的記錄。</span><span class="sxs-lookup"><span data-stu-id="4e8a9-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="4e8a9-106">下表說明可以由 UCWA 元件所撰寫的事件。</span><span class="sxs-lookup"><span data-stu-id="4e8a9-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e8a9-107">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="4e8a9-107">Event ID</span></span></th>
<th><span data-ttu-id="4e8a9-108">事件類型</span><span class="sxs-lookup"><span data-stu-id="4e8a9-108">Event Type</span></span></th>
<th><span data-ttu-id="4e8a9-109">摘要</span><span class="sxs-lookup"><span data-stu-id="4e8a9-109">Summary</span></span></th>
<th><span data-ttu-id="4e8a9-110">原因和解決方法</span><span class="sxs-lookup"><span data-stu-id="4e8a9-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-111">20001</span><span class="sxs-lookup"><span data-stu-id="4e8a9-111">20001</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-112">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-113">UCWA 初始化</span><span class="sxs-lookup"><span data-stu-id="4e8a9-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-114">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-114">N/A</span></span></p>
<p><span data-ttu-id="4e8a9-115">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-116">20002</span><span class="sxs-lookup"><span data-stu-id="4e8a9-116">20002</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-117">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-117">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-118">UCWA 發生未預期的例外狀況初始化期間</span><span class="sxs-lookup"><span data-stu-id="4e8a9-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-119">初始化期間發生未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="4e8a9-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="4e8a9-120">檢查至判斷可能的原因的相關聯的事件日誌項目中的例外狀況詳細資料</span><span class="sxs-lookup"><span data-stu-id="4e8a9-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-121">20003</span><span class="sxs-lookup"><span data-stu-id="4e8a9-121">20003</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-122">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-122">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-123">UCWA 發生未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="4e8a9-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-124">未處理的例外狀況</span><span class="sxs-lookup"><span data-stu-id="4e8a9-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="4e8a9-125">重新啟動伺服器。</span><span class="sxs-lookup"><span data-stu-id="4e8a9-125">Restart the server.</span></span> <span data-ttu-id="4e8a9-126">如果問題仍然存在連絡產品支援服務</span><span class="sxs-lookup"><span data-stu-id="4e8a9-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-127">20004</span><span class="sxs-lookup"><span data-stu-id="4e8a9-127">20004</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-128">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-128">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-129">無法存取 Exchange 的 HD 相片</span><span class="sxs-lookup"><span data-stu-id="4e8a9-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-130">連線至 Exchange 不提供</span><span class="sxs-lookup"><span data-stu-id="4e8a9-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4e8a9-131">請確定沒有可用的連線至 Exchange</span><span class="sxs-lookup"><span data-stu-id="4e8a9-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-132">20005</span><span class="sxs-lookup"><span data-stu-id="4e8a9-132">20005</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-133">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-134">從失敗的 HD 相片存取 Exchange 復原</span><span class="sxs-lookup"><span data-stu-id="4e8a9-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-135">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-136">20006</span><span class="sxs-lookup"><span data-stu-id="4e8a9-136">20006</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-137">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-137">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-138">無法存取 Exchange 連絡人搜尋</span><span class="sxs-lookup"><span data-stu-id="4e8a9-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-139">連線至 Exchange 不提供</span><span class="sxs-lookup"><span data-stu-id="4e8a9-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="4e8a9-140">請確定沒有可用的連線至 Exchange</span><span class="sxs-lookup"><span data-stu-id="4e8a9-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-141">20007</span><span class="sxs-lookup"><span data-stu-id="4e8a9-141">20007</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-142">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-143">復原從 Exchange 中搜尋連絡人失敗</span><span class="sxs-lookup"><span data-stu-id="4e8a9-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-144">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-145">20008</span><span class="sxs-lookup"><span data-stu-id="4e8a9-145">20008</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-146">警告</span><span class="sxs-lookup"><span data-stu-id="4e8a9-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-147">嘗試將超過每個應用程式的允許的目前狀態訂閱訂閱</span><span class="sxs-lookup"><span data-stu-id="4e8a9-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-148">嘗試將超過每個應用程式的允許的目前狀態訂閱訂閱</span><span class="sxs-lookup"><span data-stu-id="4e8a9-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="4e8a9-149">檢查不必要的訂用帳戶的用戶端</span><span class="sxs-lookup"><span data-stu-id="4e8a9-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-150">20009</span><span class="sxs-lookup"><span data-stu-id="4e8a9-150">20009</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-151">警告</span><span class="sxs-lookup"><span data-stu-id="4e8a9-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-152">嘗試將超過允許的目前狀態訂閱，每個批次訂閱</span><span class="sxs-lookup"><span data-stu-id="4e8a9-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-153">嘗試將超過允許的目前狀態訂閱，每個批次訂閱</span><span class="sxs-lookup"><span data-stu-id="4e8a9-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="4e8a9-154">檢查不必要的訂用帳戶的用戶端</span><span class="sxs-lookup"><span data-stu-id="4e8a9-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-155">20010</span><span class="sxs-lookup"><span data-stu-id="4e8a9-155">20010</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-156">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-156">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-157">無法擷取 inband 資料</span><span class="sxs-lookup"><span data-stu-id="4e8a9-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-158">無法擷取 inband 資料</span><span class="sxs-lookup"><span data-stu-id="4e8a9-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="4e8a9-159">如果問題仍然存在連絡產品支援服務</span><span class="sxs-lookup"><span data-stu-id="4e8a9-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-160">20011</span><span class="sxs-lookup"><span data-stu-id="4e8a9-160">20011</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-161">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-161">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-162">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="4e8a9-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-163">無法訂閱目前狀態</span><span class="sxs-lookup"><span data-stu-id="4e8a9-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="4e8a9-164">如果問題仍然存在連絡產品支援服務</span><span class="sxs-lookup"><span data-stu-id="4e8a9-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-165">20012</span><span class="sxs-lookup"><span data-stu-id="4e8a9-165">20012</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-166">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-166">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-167">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="4e8a9-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-168">無法註冊端點</span><span class="sxs-lookup"><span data-stu-id="4e8a9-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="4e8a9-169">如果問題仍然存在連絡產品支援服務</span><span class="sxs-lookup"><span data-stu-id="4e8a9-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-170">20013</span><span class="sxs-lookup"><span data-stu-id="4e8a9-170">20013</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-171">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-171">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-172">IM MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-173">IM MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e8a9-174">請參閱 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-175">20014</span><span class="sxs-lookup"><span data-stu-id="4e8a9-175">20014</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-176">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-177">從連線至 IM MCU 失敗復原</span><span class="sxs-lookup"><span data-stu-id="4e8a9-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-178">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-179">20015</span><span class="sxs-lookup"><span data-stu-id="4e8a9-179">20015</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-180">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-180">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-181">AV MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-182">AV MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e8a9-183">請參閱 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-184">20016</span><span class="sxs-lookup"><span data-stu-id="4e8a9-184">20016</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-185">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-186">從連線至 AV MCU 失敗復原</span><span class="sxs-lookup"><span data-stu-id="4e8a9-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-187">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-188">20017</span><span class="sxs-lookup"><span data-stu-id="4e8a9-188">20017</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-189">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-189">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-190">無法使用此 MCU 為</span><span class="sxs-lookup"><span data-stu-id="4e8a9-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-191">無法使用此 MCU 為</span><span class="sxs-lookup"><span data-stu-id="4e8a9-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e8a9-192">請參閱 AS MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-193">20018</span><span class="sxs-lookup"><span data-stu-id="4e8a9-193">20018</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-194">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-195">從連線至 AS MCU 失敗復原</span><span class="sxs-lookup"><span data-stu-id="4e8a9-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-196">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-197">20019</span><span class="sxs-lookup"><span data-stu-id="4e8a9-197">20019</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-198">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-198">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-199">資料 MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-200">資料 MCU 是無法使用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="4e8a9-201">請參閱資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-202">20020</span><span class="sxs-lookup"><span data-stu-id="4e8a9-202">20020</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-203">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-204">從連線至資料 MCU 失敗復原</span><span class="sxs-lookup"><span data-stu-id="4e8a9-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-205">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-206">20021</span><span class="sxs-lookup"><span data-stu-id="4e8a9-206">20021</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-207">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-207">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-208">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-209">無法加入 IM MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="4e8a9-210">請參閱 IM MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-211">20022</span><span class="sxs-lookup"><span data-stu-id="4e8a9-211">20022</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-212">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-212">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-213">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-214">無法加入 AV MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="4e8a9-215">請參閱 AV MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-216">20023</span><span class="sxs-lookup"><span data-stu-id="4e8a9-216">20023</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-217">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-217">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-218">無法加入 AS MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-219">無法加入 AS MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="4e8a9-220">請參閱 AS MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-221">20024</span><span class="sxs-lookup"><span data-stu-id="4e8a9-221">20024</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-222">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-222">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-223">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-224">無法加入資料 MCU</span><span class="sxs-lookup"><span data-stu-id="4e8a9-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="4e8a9-225">請參閱資料 MCU 是否正在執行</span><span class="sxs-lookup"><span data-stu-id="4e8a9-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-226">20025</span><span class="sxs-lookup"><span data-stu-id="4e8a9-226">20025</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-227">Error</span><span class="sxs-lookup"><span data-stu-id="4e8a9-227">Error</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-228">無法存取 active directory 中的相片</span><span class="sxs-lookup"><span data-stu-id="4e8a9-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-229">Active directory 連線不提供</span><span class="sxs-lookup"><span data-stu-id="4e8a9-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="4e8a9-230">請確定沒有可用的 active directory 連線</span><span class="sxs-lookup"><span data-stu-id="4e8a9-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e8a9-231">20026</span><span class="sxs-lookup"><span data-stu-id="4e8a9-231">20026</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-232">資訊性</span><span class="sxs-lookup"><span data-stu-id="4e8a9-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-233">復原從失敗的存取 active directory 中的相片</span><span class="sxs-lookup"><span data-stu-id="4e8a9-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-234">不適用</span><span class="sxs-lookup"><span data-stu-id="4e8a9-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e8a9-235">20027</span><span class="sxs-lookup"><span data-stu-id="4e8a9-235">20027</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-236">警告</span><span class="sxs-lookup"><span data-stu-id="4e8a9-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-237">無法還原序列化的 labs.core.ilabobject</span><span class="sxs-lookup"><span data-stu-id="4e8a9-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="4e8a9-238">無法還原序列化的 labs.core.ilabobject</span><span class="sxs-lookup"><span data-stu-id="4e8a9-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="4e8a9-239">如果問題仍然存在連絡產品支援服務</span><span class="sxs-lookup"><span data-stu-id="4e8a9-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

