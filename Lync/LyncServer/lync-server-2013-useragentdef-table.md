---
title: Lync Server 2013： UserAgentDef 表格
description: Lync Server 2013： UserAgentDef 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgentDef table
ms:assetid: 96c49239-d999-4045-8b64-9d1940cce8ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205100(v=OCS.15)
ms:contentKeyID: 48184860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b12239d0d6ba6e04a708708a1740dbf02c0e07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548639"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="85ed5-103">Lync Server 2013 中的 UserAgentDef 表格</span><span class="sxs-lookup"><span data-stu-id="85ed5-103">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85ed5-104">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="85ed5-104">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="85ed5-105">UserAgentDef 表會將使用者代理程式識別碼對應到代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="85ed5-105">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="85ed5-106">使用者代理程式是用來連接至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="85ed5-106">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="85ed5-107">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="85ed5-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85ed5-108">UAType</span><span class="sxs-lookup"><span data-stu-id="85ed5-108">UAType</span></span></th>
<th><span data-ttu-id="85ed5-109">UAName</span><span class="sxs-lookup"><span data-stu-id="85ed5-109">UAName</span></span></th>
<th><span data-ttu-id="85ed5-110">UACategory</span><span class="sxs-lookup"><span data-stu-id="85ed5-110">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-111">1 </span><span class="sxs-lookup"><span data-stu-id="85ed5-111">1</span></span></p></td>
<td><p><span data-ttu-id="85ed5-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="85ed5-112">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="85ed5-113">MediationServer</span><span class="sxs-lookup"><span data-stu-id="85ed5-113">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-114">第</span><span class="sxs-lookup"><span data-stu-id="85ed5-114">2</span></span></p></td>
<td><p><span data-ttu-id="85ed5-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="85ed5-115">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="85ed5-116">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="85ed5-116">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-117">4 </span><span class="sxs-lookup"><span data-stu-id="85ed5-117">4</span></span></p></td>
<td><p><span data-ttu-id="85ed5-118">Oc</span><span class="sxs-lookup"><span data-stu-id="85ed5-118">OC</span></span></p></td>
<td><p><span data-ttu-id="85ed5-119">Oc</span><span class="sxs-lookup"><span data-stu-id="85ed5-119">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-120">8 </span><span class="sxs-lookup"><span data-stu-id="85ed5-120">8</span></span></p></td>
<td><p><span data-ttu-id="85ed5-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="85ed5-121">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="85ed5-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="85ed5-122">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-123">16 </span><span class="sxs-lookup"><span data-stu-id="85ed5-123">16</span></span></p></td>
<td><p><span data-ttu-id="85ed5-124">LMC</span><span class="sxs-lookup"><span data-stu-id="85ed5-124">LMC</span></span></p></td>
<td><p><span data-ttu-id="85ed5-125">LMC</span><span class="sxs-lookup"><span data-stu-id="85ed5-125">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-126">32</span><span class="sxs-lookup"><span data-stu-id="85ed5-126">32</span></span></p></td>
<td><p><span data-ttu-id="85ed5-127">Dvt</span><span class="sxs-lookup"><span data-stu-id="85ed5-127">DVT</span></span></p></td>
<td><p><span data-ttu-id="85ed5-128">Dvt</span><span class="sxs-lookup"><span data-stu-id="85ed5-128">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-129">64</span><span class="sxs-lookup"><span data-stu-id="85ed5-129">64</span></span></p></td>
<td><p><span data-ttu-id="85ed5-130">毫米</span><span class="sxs-lookup"><span data-stu-id="85ed5-130">MM</span></span></p></td>
<td><p><span data-ttu-id="85ed5-131">毫米</span><span class="sxs-lookup"><span data-stu-id="85ed5-131">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-132">64</span><span class="sxs-lookup"><span data-stu-id="85ed5-132">64</span></span></p></td>
<td><p><span data-ttu-id="85ed5-133">Mc</span><span class="sxs-lookup"><span data-stu-id="85ed5-133">MC</span></span></p></td>
<td><p><span data-ttu-id="85ed5-134">毫米</span><span class="sxs-lookup"><span data-stu-id="85ed5-134">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-135">128</span><span class="sxs-lookup"><span data-stu-id="85ed5-135">128</span></span></p></td>
<td><p><span data-ttu-id="85ed5-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="85ed5-136">Attendant</span></span></p></td>
<td><p><span data-ttu-id="85ed5-137">語音應答</span><span class="sxs-lookup"><span data-stu-id="85ed5-137">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-138">256</span><span class="sxs-lookup"><span data-stu-id="85ed5-138">256</span></span></p></td>
<td><p><span data-ttu-id="85ed5-139">Conferencing_Announcement_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="85ed5-139">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="85ed5-140">Cas</span><span class="sxs-lookup"><span data-stu-id="85ed5-140">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-141">512</span><span class="sxs-lookup"><span data-stu-id="85ed5-141">512</span></span></p></td>
<td><p><span data-ttu-id="85ed5-142">Conferencing_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="85ed5-142">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="85ed5-143">Caa</span><span class="sxs-lookup"><span data-stu-id="85ed5-143">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-144">512</span><span class="sxs-lookup"><span data-stu-id="85ed5-144">512</span></span></p></td>
<td><p><span data-ttu-id="85ed5-145">Conference_Auto_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="85ed5-145">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="85ed5-146">Caa</span><span class="sxs-lookup"><span data-stu-id="85ed5-146">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-147">1024</span><span class="sxs-lookup"><span data-stu-id="85ed5-147">1024</span></span></p></td>
<td><p><span data-ttu-id="85ed5-148">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="85ed5-148">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="85ed5-149">RG</span><span class="sxs-lookup"><span data-stu-id="85ed5-149">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-150">1032</span><span class="sxs-lookup"><span data-stu-id="85ed5-150">1032</span></span></p></td>
<td><p><span data-ttu-id="85ed5-151">Call_Park_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="85ed5-151">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="85ed5-152">Cps</span><span class="sxs-lookup"><span data-stu-id="85ed5-152">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-153">1040</span><span class="sxs-lookup"><span data-stu-id="85ed5-153">1040</span></span></p></td>
<td><p><span data-ttu-id="85ed5-154">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="85ed5-154">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="85ed5-155">AS</span><span class="sxs-lookup"><span data-stu-id="85ed5-155">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-156">2048</span><span class="sxs-lookup"><span data-stu-id="85ed5-156">2048</span></span></p></td>
<td><p><span data-ttu-id="85ed5-157">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="85ed5-157">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="85ed5-158">Ccs</span><span class="sxs-lookup"><span data-stu-id="85ed5-158">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-159">16386</span><span class="sxs-lookup"><span data-stu-id="85ed5-159">16386</span></span></p></td>
<td><p><span data-ttu-id="85ed5-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="85ed5-160">CoMo</span></span></p></td>
<td><p><span data-ttu-id="85ed5-161">CoMo</span><span class="sxs-lookup"><span data-stu-id="85ed5-161">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-162">16387</span><span class="sxs-lookup"><span data-stu-id="85ed5-162">16387</span></span></p></td>
<td><p><span data-ttu-id="85ed5-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="85ed5-163">CWA</span></span></p></td>
<td><p><span data-ttu-id="85ed5-164">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="85ed5-164">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-165">16388</span><span class="sxs-lookup"><span data-stu-id="85ed5-165">16388</span></span></p></td>
<td><p><span data-ttu-id="85ed5-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="85ed5-166">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="85ed5-167">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="85ed5-167">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-168">16389</span><span class="sxs-lookup"><span data-stu-id="85ed5-168">16389</span></span></p></td>
<td><p><span data-ttu-id="85ed5-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="85ed5-169">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="85ed5-170">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="85ed5-170">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-171">16393</span><span class="sxs-lookup"><span data-stu-id="85ed5-171">16393</span></span></p></td>
<td><p><span data-ttu-id="85ed5-172">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="85ed5-172">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="85ed5-173">ExUM</span><span class="sxs-lookup"><span data-stu-id="85ed5-173">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-174">16395</span><span class="sxs-lookup"><span data-stu-id="85ed5-174">16395</span></span></p></td>
<td><p><span data-ttu-id="85ed5-175">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="85ed5-175">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="85ed5-176">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="85ed5-176">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-177">16396</span><span class="sxs-lookup"><span data-stu-id="85ed5-177">16396</span></span></p></td>
<td><p><span data-ttu-id="85ed5-178">聖</span><span class="sxs-lookup"><span data-stu-id="85ed5-178">ST</span></span></p></td>
<td><p><span data-ttu-id="85ed5-179">聖</span><span class="sxs-lookup"><span data-stu-id="85ed5-179">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-180">16397</span><span class="sxs-lookup"><span data-stu-id="85ed5-180">16397</span></span></p></td>
<td><p><span data-ttu-id="85ed5-181">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="85ed5-181">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="85ed5-182">ASMCU</span><span class="sxs-lookup"><span data-stu-id="85ed5-182">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-183">16398</span><span class="sxs-lookup"><span data-stu-id="85ed5-183">16398</span></span></p></td>
<td><p><span data-ttu-id="85ed5-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-184">WPLync</span></span></p></td>
<td><p><span data-ttu-id="85ed5-185">WPLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-185">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-186">16399</span><span class="sxs-lookup"><span data-stu-id="85ed5-186">16399</span></span></p></td>
<td><p><span data-ttu-id="85ed5-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-187">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="85ed5-188">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-188">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-189">16400</span><span class="sxs-lookup"><span data-stu-id="85ed5-189">16400</span></span></p></td>
<td><p><span data-ttu-id="85ed5-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-190">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="85ed5-191">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-191">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-192">16401</span><span class="sxs-lookup"><span data-stu-id="85ed5-192">16401</span></span></p></td>
<td><p><span data-ttu-id="85ed5-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-193">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="85ed5-194">iPadLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-194">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-195">16402</span><span class="sxs-lookup"><span data-stu-id="85ed5-195">16402</span></span></p></td>
<td><p><span data-ttu-id="85ed5-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-196">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="85ed5-197">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="85ed5-197">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-198">16403</span><span class="sxs-lookup"><span data-stu-id="85ed5-198">16403</span></span></p></td>
<td><p><span data-ttu-id="85ed5-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="85ed5-199">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="85ed5-200">LyncImm</span><span class="sxs-lookup"><span data-stu-id="85ed5-200">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-201">16404</span><span class="sxs-lookup"><span data-stu-id="85ed5-201">16404</span></span></p></td>
<td><p><span data-ttu-id="85ed5-202">個人電腦</span><span class="sxs-lookup"><span data-stu-id="85ed5-202">PCS</span></span></p></td>
<td><p><span data-ttu-id="85ed5-203">個人電腦</span><span class="sxs-lookup"><span data-stu-id="85ed5-203">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-204">16405</span><span class="sxs-lookup"><span data-stu-id="85ed5-204">16405</span></span></p></td>
<td><p><span data-ttu-id="85ed5-205">LWA</span><span class="sxs-lookup"><span data-stu-id="85ed5-205">LWA</span></span></p></td>
<td><p><span data-ttu-id="85ed5-206">LWA</span><span class="sxs-lookup"><span data-stu-id="85ed5-206">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-207">16406</span><span class="sxs-lookup"><span data-stu-id="85ed5-207">16406</span></span></p></td>
<td><p><span data-ttu-id="85ed5-208">OWA</span><span class="sxs-lookup"><span data-stu-id="85ed5-208">OWA</span></span></p></td>
<td><p><span data-ttu-id="85ed5-209">OWA</span><span class="sxs-lookup"><span data-stu-id="85ed5-209">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-210">16407</span><span class="sxs-lookup"><span data-stu-id="85ed5-210">16407</span></span></p></td>
<td><p><span data-ttu-id="85ed5-211">Aoc</span><span class="sxs-lookup"><span data-stu-id="85ed5-211">AOC</span></span></p></td>
<td><p><span data-ttu-id="85ed5-212">Aoc</span><span class="sxs-lookup"><span data-stu-id="85ed5-212">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-213">16408</span><span class="sxs-lookup"><span data-stu-id="85ed5-213">16408</span></span></p></td>
<td><p><span data-ttu-id="85ed5-214">GCC</span><span class="sxs-lookup"><span data-stu-id="85ed5-214">GCC</span></span></p></td>
<td><p><span data-ttu-id="85ed5-215">GCC</span><span class="sxs-lookup"><span data-stu-id="85ed5-215">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-216">16409</span><span class="sxs-lookup"><span data-stu-id="85ed5-216">16409</span></span></p></td>
<td><p><span data-ttu-id="85ed5-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="85ed5-217">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="85ed5-218">IMMCU</span><span class="sxs-lookup"><span data-stu-id="85ed5-218">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-219">16410</span><span class="sxs-lookup"><span data-stu-id="85ed5-219">16410</span></span></p></td>
<td><p><span data-ttu-id="85ed5-220">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="85ed5-220">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="85ed5-221">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="85ed5-221">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85ed5-222">32769</span><span class="sxs-lookup"><span data-stu-id="85ed5-222">32769</span></span></p></td>
<td><p><span data-ttu-id="85ed5-223">閘道</span><span class="sxs-lookup"><span data-stu-id="85ed5-223">Gateway</span></span></p></td>
<td><p><span data-ttu-id="85ed5-224">閘道</span><span class="sxs-lookup"><span data-stu-id="85ed5-224">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85ed5-225">32770</span><span class="sxs-lookup"><span data-stu-id="85ed5-225">32770</span></span></p></td>
<td><p><span data-ttu-id="85ed5-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="85ed5-226">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="85ed5-227">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="85ed5-227">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

