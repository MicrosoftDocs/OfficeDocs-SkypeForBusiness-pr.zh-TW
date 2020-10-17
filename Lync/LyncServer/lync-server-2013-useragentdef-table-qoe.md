---
title: 'Lync Server 2013： UserAgentDef table (QoE) '
description: Lync Server 2013： UserAgentDef table (QoE) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8546a33e607524b23755e9abf3edb2d5e2e417d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547339"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="7b262-103">在 Lync Server 2013 中 UserAgentDef table (QoE) </span><span class="sxs-lookup"><span data-stu-id="7b262-103">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b262-104">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="7b262-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="7b262-105">UserAgentDef 表會將使用者代理程式識別碼對應到代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="7b262-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="7b262-106">使用者代理程式是用來連接至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="7b262-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b262-107">UAType</span><span class="sxs-lookup"><span data-stu-id="7b262-107">UAType</span></span></th>
<th><span data-ttu-id="7b262-108">UAName</span><span class="sxs-lookup"><span data-stu-id="7b262-108">UAName</span></span></th>
<th><span data-ttu-id="7b262-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="7b262-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b262-110">1 </span><span class="sxs-lookup"><span data-stu-id="7b262-110">1</span></span></p></td>
<td><p><span data-ttu-id="7b262-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="7b262-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="7b262-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="7b262-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-113">第</span><span class="sxs-lookup"><span data-stu-id="7b262-113">2</span></span></p></td>
<td><p><span data-ttu-id="7b262-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="7b262-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="7b262-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="7b262-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-116">4 </span><span class="sxs-lookup"><span data-stu-id="7b262-116">4</span></span></p></td>
<td><p><span data-ttu-id="7b262-117">Oc</span><span class="sxs-lookup"><span data-stu-id="7b262-117">OC</span></span></p></td>
<td><p><span data-ttu-id="7b262-118">Oc</span><span class="sxs-lookup"><span data-stu-id="7b262-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-119">8 </span><span class="sxs-lookup"><span data-stu-id="7b262-119">8</span></span></p></td>
<td><p><span data-ttu-id="7b262-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="7b262-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="7b262-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="7b262-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-122">16 </span><span class="sxs-lookup"><span data-stu-id="7b262-122">16</span></span></p></td>
<td><p><span data-ttu-id="7b262-123">LMC</span><span class="sxs-lookup"><span data-stu-id="7b262-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="7b262-124">LMC</span><span class="sxs-lookup"><span data-stu-id="7b262-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-125">32</span><span class="sxs-lookup"><span data-stu-id="7b262-125">32</span></span></p></td>
<td><p><span data-ttu-id="7b262-126">Dvt</span><span class="sxs-lookup"><span data-stu-id="7b262-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="7b262-127">Dvt</span><span class="sxs-lookup"><span data-stu-id="7b262-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-128">64</span><span class="sxs-lookup"><span data-stu-id="7b262-128">64</span></span></p></td>
<td><p><span data-ttu-id="7b262-129">毫米</span><span class="sxs-lookup"><span data-stu-id="7b262-129">MM</span></span></p></td>
<td><p><span data-ttu-id="7b262-130">毫米</span><span class="sxs-lookup"><span data-stu-id="7b262-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-131">64</span><span class="sxs-lookup"><span data-stu-id="7b262-131">64</span></span></p></td>
<td><p><span data-ttu-id="7b262-132">Mc</span><span class="sxs-lookup"><span data-stu-id="7b262-132">MC</span></span></p></td>
<td><p><span data-ttu-id="7b262-133">毫米</span><span class="sxs-lookup"><span data-stu-id="7b262-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-134">128</span><span class="sxs-lookup"><span data-stu-id="7b262-134">128</span></span></p></td>
<td><p><span data-ttu-id="7b262-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="7b262-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="7b262-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="7b262-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-137">256</span><span class="sxs-lookup"><span data-stu-id="7b262-137">256</span></span></p></td>
<td><p><span data-ttu-id="7b262-138">Conferencing_Announcement_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="7b262-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="7b262-139">Cas</span><span class="sxs-lookup"><span data-stu-id="7b262-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-140">512</span><span class="sxs-lookup"><span data-stu-id="7b262-140">512</span></span></p></td>
<td><p><span data-ttu-id="7b262-141">Conferencing_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="7b262-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="7b262-142">Caa</span><span class="sxs-lookup"><span data-stu-id="7b262-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-143">512</span><span class="sxs-lookup"><span data-stu-id="7b262-143">512</span></span></p></td>
<td><p><span data-ttu-id="7b262-144">Conference_Auto_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="7b262-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="7b262-145">Caa</span><span class="sxs-lookup"><span data-stu-id="7b262-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-146">1024</span><span class="sxs-lookup"><span data-stu-id="7b262-146">1024</span></span></p></td>
<td><p><span data-ttu-id="7b262-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="7b262-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="7b262-148">RG</span><span class="sxs-lookup"><span data-stu-id="7b262-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-149">1032</span><span class="sxs-lookup"><span data-stu-id="7b262-149">1032</span></span></p></td>
<td><p><span data-ttu-id="7b262-150">Call_Park_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="7b262-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="7b262-151">Cps</span><span class="sxs-lookup"><span data-stu-id="7b262-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-152">1040</span><span class="sxs-lookup"><span data-stu-id="7b262-152">1040</span></span></p></td>
<td><p><span data-ttu-id="7b262-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="7b262-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="7b262-154">AS</span><span class="sxs-lookup"><span data-stu-id="7b262-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-155">2048</span><span class="sxs-lookup"><span data-stu-id="7b262-155">2048</span></span></p></td>
<td><p><span data-ttu-id="7b262-156">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="7b262-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="7b262-157">Ccs</span><span class="sxs-lookup"><span data-stu-id="7b262-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-158">16386</span><span class="sxs-lookup"><span data-stu-id="7b262-158">16386</span></span></p></td>
<td><p><span data-ttu-id="7b262-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="7b262-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="7b262-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="7b262-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-161">16387</span><span class="sxs-lookup"><span data-stu-id="7b262-161">16387</span></span></p></td>
<td><p><span data-ttu-id="7b262-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="7b262-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="7b262-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="7b262-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-164">16388</span><span class="sxs-lookup"><span data-stu-id="7b262-164">16388</span></span></p></td>
<td><p><span data-ttu-id="7b262-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="7b262-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="7b262-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="7b262-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-167">16389</span><span class="sxs-lookup"><span data-stu-id="7b262-167">16389</span></span></p></td>
<td><p><span data-ttu-id="7b262-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="7b262-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="7b262-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="7b262-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-170">16393</span><span class="sxs-lookup"><span data-stu-id="7b262-170">16393</span></span></p></td>
<td><p><span data-ttu-id="7b262-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="7b262-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="7b262-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="7b262-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-173">16395</span><span class="sxs-lookup"><span data-stu-id="7b262-173">16395</span></span></p></td>
<td><p><span data-ttu-id="7b262-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="7b262-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="7b262-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="7b262-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-176">16396</span><span class="sxs-lookup"><span data-stu-id="7b262-176">16396</span></span></p></td>
<td><p><span data-ttu-id="7b262-177">聖</span><span class="sxs-lookup"><span data-stu-id="7b262-177">ST</span></span></p></td>
<td><p><span data-ttu-id="7b262-178">聖</span><span class="sxs-lookup"><span data-stu-id="7b262-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-179">16397</span><span class="sxs-lookup"><span data-stu-id="7b262-179">16397</span></span></p></td>
<td><p><span data-ttu-id="7b262-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="7b262-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="7b262-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="7b262-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-182">16398</span><span class="sxs-lookup"><span data-stu-id="7b262-182">16398</span></span></p></td>
<td><p><span data-ttu-id="7b262-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="7b262-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="7b262-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="7b262-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-185">16399</span><span class="sxs-lookup"><span data-stu-id="7b262-185">16399</span></span></p></td>
<td><p><span data-ttu-id="7b262-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="7b262-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="7b262-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="7b262-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-188">16400</span><span class="sxs-lookup"><span data-stu-id="7b262-188">16400</span></span></p></td>
<td><p><span data-ttu-id="7b262-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="7b262-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="7b262-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="7b262-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-191">16401</span><span class="sxs-lookup"><span data-stu-id="7b262-191">16401</span></span></p></td>
<td><p><span data-ttu-id="7b262-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="7b262-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="7b262-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="7b262-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-194">16402</span><span class="sxs-lookup"><span data-stu-id="7b262-194">16402</span></span></p></td>
<td><p><span data-ttu-id="7b262-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="7b262-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="7b262-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="7b262-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-197">16403</span><span class="sxs-lookup"><span data-stu-id="7b262-197">16403</span></span></p></td>
<td><p><span data-ttu-id="7b262-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="7b262-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="7b262-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="7b262-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-200">16404</span><span class="sxs-lookup"><span data-stu-id="7b262-200">16404</span></span></p></td>
<td><p><span data-ttu-id="7b262-201">個人電腦</span><span class="sxs-lookup"><span data-stu-id="7b262-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="7b262-202">個人電腦</span><span class="sxs-lookup"><span data-stu-id="7b262-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-203">16405</span><span class="sxs-lookup"><span data-stu-id="7b262-203">16405</span></span></p></td>
<td><p><span data-ttu-id="7b262-204">LWA</span><span class="sxs-lookup"><span data-stu-id="7b262-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="7b262-205">LWA</span><span class="sxs-lookup"><span data-stu-id="7b262-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-206">16406</span><span class="sxs-lookup"><span data-stu-id="7b262-206">16406</span></span></p></td>
<td><p><span data-ttu-id="7b262-207">OWA</span><span class="sxs-lookup"><span data-stu-id="7b262-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="7b262-208">OWA</span><span class="sxs-lookup"><span data-stu-id="7b262-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-209">16407</span><span class="sxs-lookup"><span data-stu-id="7b262-209">16407</span></span></p></td>
<td><p><span data-ttu-id="7b262-210">Aoc</span><span class="sxs-lookup"><span data-stu-id="7b262-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="7b262-211">Aoc</span><span class="sxs-lookup"><span data-stu-id="7b262-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-212">16408</span><span class="sxs-lookup"><span data-stu-id="7b262-212">16408</span></span></p></td>
<td><p><span data-ttu-id="7b262-213">GCC</span><span class="sxs-lookup"><span data-stu-id="7b262-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="7b262-214">GCC</span><span class="sxs-lookup"><span data-stu-id="7b262-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-215">16409</span><span class="sxs-lookup"><span data-stu-id="7b262-215">16409</span></span></p></td>
<td><p><span data-ttu-id="7b262-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="7b262-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="7b262-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="7b262-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-218">16410</span><span class="sxs-lookup"><span data-stu-id="7b262-218">16410</span></span></p></td>
<td><p><span data-ttu-id="7b262-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="7b262-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="7b262-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="7b262-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b262-221">32769</span><span class="sxs-lookup"><span data-stu-id="7b262-221">32769</span></span></p></td>
<td><p><span data-ttu-id="7b262-222">閘道</span><span class="sxs-lookup"><span data-stu-id="7b262-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="7b262-223">閘道</span><span class="sxs-lookup"><span data-stu-id="7b262-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b262-224">32770</span><span class="sxs-lookup"><span data-stu-id="7b262-224">32770</span></span></p></td>
<td><p><span data-ttu-id="7b262-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="7b262-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="7b262-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="7b262-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

