---
title: Lync Server 2013： UserAgentDef 表格
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
ms.openlocfilehash: 2ef005350d5ed9a4dee3f108a4cf9e3349389d1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530070"
---
# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="9b461-102">Lync Server 2013 中的 UserAgentDef 表格</span><span class="sxs-lookup"><span data-stu-id="9b461-102">UserAgentDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b461-103">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="9b461-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="9b461-104">UserAgentDef 表會將使用者代理程式識別碼對應到代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="9b461-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="9b461-105">使用者代理程式是用來連接至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="9b461-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="9b461-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9b461-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b461-107">UAType</span><span class="sxs-lookup"><span data-stu-id="9b461-107">UAType</span></span></th>
<th><span data-ttu-id="9b461-108">UAName</span><span class="sxs-lookup"><span data-stu-id="9b461-108">UAName</span></span></th>
<th><span data-ttu-id="9b461-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="9b461-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b461-110">1 </span><span class="sxs-lookup"><span data-stu-id="9b461-110">1</span></span></p></td>
<td><p><span data-ttu-id="9b461-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="9b461-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="9b461-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="9b461-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-113">第</span><span class="sxs-lookup"><span data-stu-id="9b461-113">2</span></span></p></td>
<td><p><span data-ttu-id="9b461-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="9b461-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="9b461-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="9b461-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-116">4 </span><span class="sxs-lookup"><span data-stu-id="9b461-116">4</span></span></p></td>
<td><p><span data-ttu-id="9b461-117">Oc</span><span class="sxs-lookup"><span data-stu-id="9b461-117">OC</span></span></p></td>
<td><p><span data-ttu-id="9b461-118">Oc</span><span class="sxs-lookup"><span data-stu-id="9b461-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-119">8 </span><span class="sxs-lookup"><span data-stu-id="9b461-119">8</span></span></p></td>
<td><p><span data-ttu-id="9b461-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9b461-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="9b461-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9b461-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-122">16 </span><span class="sxs-lookup"><span data-stu-id="9b461-122">16</span></span></p></td>
<td><p><span data-ttu-id="9b461-123">LMC</span><span class="sxs-lookup"><span data-stu-id="9b461-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="9b461-124">LMC</span><span class="sxs-lookup"><span data-stu-id="9b461-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-125">32</span><span class="sxs-lookup"><span data-stu-id="9b461-125">32</span></span></p></td>
<td><p><span data-ttu-id="9b461-126">Dvt</span><span class="sxs-lookup"><span data-stu-id="9b461-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="9b461-127">Dvt</span><span class="sxs-lookup"><span data-stu-id="9b461-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-128">64</span><span class="sxs-lookup"><span data-stu-id="9b461-128">64</span></span></p></td>
<td><p><span data-ttu-id="9b461-129">毫米</span><span class="sxs-lookup"><span data-stu-id="9b461-129">MM</span></span></p></td>
<td><p><span data-ttu-id="9b461-130">毫米</span><span class="sxs-lookup"><span data-stu-id="9b461-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-131">64</span><span class="sxs-lookup"><span data-stu-id="9b461-131">64</span></span></p></td>
<td><p><span data-ttu-id="9b461-132">Mc</span><span class="sxs-lookup"><span data-stu-id="9b461-132">MC</span></span></p></td>
<td><p><span data-ttu-id="9b461-133">毫米</span><span class="sxs-lookup"><span data-stu-id="9b461-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-134">128</span><span class="sxs-lookup"><span data-stu-id="9b461-134">128</span></span></p></td>
<td><p><span data-ttu-id="9b461-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="9b461-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="9b461-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="9b461-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-137">256</span><span class="sxs-lookup"><span data-stu-id="9b461-137">256</span></span></p></td>
<td><p><span data-ttu-id="9b461-138">Conferencing_Announcement_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="9b461-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="9b461-139">Cas</span><span class="sxs-lookup"><span data-stu-id="9b461-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-140">512</span><span class="sxs-lookup"><span data-stu-id="9b461-140">512</span></span></p></td>
<td><p><span data-ttu-id="9b461-141">Conferencing_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="9b461-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="9b461-142">Caa</span><span class="sxs-lookup"><span data-stu-id="9b461-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-143">512</span><span class="sxs-lookup"><span data-stu-id="9b461-143">512</span></span></p></td>
<td><p><span data-ttu-id="9b461-144">Conference_Auto_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="9b461-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="9b461-145">Caa</span><span class="sxs-lookup"><span data-stu-id="9b461-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-146">1024</span><span class="sxs-lookup"><span data-stu-id="9b461-146">1024</span></span></p></td>
<td><p><span data-ttu-id="9b461-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="9b461-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="9b461-148">RG</span><span class="sxs-lookup"><span data-stu-id="9b461-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-149">1032</span><span class="sxs-lookup"><span data-stu-id="9b461-149">1032</span></span></p></td>
<td><p><span data-ttu-id="9b461-150">Call_Park_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="9b461-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="9b461-151">Cps</span><span class="sxs-lookup"><span data-stu-id="9b461-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-152">1040</span><span class="sxs-lookup"><span data-stu-id="9b461-152">1040</span></span></p></td>
<td><p><span data-ttu-id="9b461-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="9b461-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="9b461-154">AS</span><span class="sxs-lookup"><span data-stu-id="9b461-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-155">2048</span><span class="sxs-lookup"><span data-stu-id="9b461-155">2048</span></span></p></td>
<td><p><span data-ttu-id="9b461-156">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="9b461-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="9b461-157">Ccs</span><span class="sxs-lookup"><span data-stu-id="9b461-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-158">16386</span><span class="sxs-lookup"><span data-stu-id="9b461-158">16386</span></span></p></td>
<td><p><span data-ttu-id="9b461-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="9b461-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="9b461-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="9b461-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-161">16387</span><span class="sxs-lookup"><span data-stu-id="9b461-161">16387</span></span></p></td>
<td><p><span data-ttu-id="9b461-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="9b461-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="9b461-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="9b461-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-164">16388</span><span class="sxs-lookup"><span data-stu-id="9b461-164">16388</span></span></p></td>
<td><p><span data-ttu-id="9b461-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="9b461-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="9b461-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="9b461-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-167">16389</span><span class="sxs-lookup"><span data-stu-id="9b461-167">16389</span></span></p></td>
<td><p><span data-ttu-id="9b461-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="9b461-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="9b461-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="9b461-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-170">16393</span><span class="sxs-lookup"><span data-stu-id="9b461-170">16393</span></span></p></td>
<td><p><span data-ttu-id="9b461-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="9b461-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="9b461-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="9b461-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-173">16395</span><span class="sxs-lookup"><span data-stu-id="9b461-173">16395</span></span></p></td>
<td><p><span data-ttu-id="9b461-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="9b461-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="9b461-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="9b461-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-176">16396</span><span class="sxs-lookup"><span data-stu-id="9b461-176">16396</span></span></p></td>
<td><p><span data-ttu-id="9b461-177">聖</span><span class="sxs-lookup"><span data-stu-id="9b461-177">ST</span></span></p></td>
<td><p><span data-ttu-id="9b461-178">聖</span><span class="sxs-lookup"><span data-stu-id="9b461-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-179">16397</span><span class="sxs-lookup"><span data-stu-id="9b461-179">16397</span></span></p></td>
<td><p><span data-ttu-id="9b461-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="9b461-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="9b461-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="9b461-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-182">16398</span><span class="sxs-lookup"><span data-stu-id="9b461-182">16398</span></span></p></td>
<td><p><span data-ttu-id="9b461-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="9b461-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="9b461-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="9b461-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-185">16399</span><span class="sxs-lookup"><span data-stu-id="9b461-185">16399</span></span></p></td>
<td><p><span data-ttu-id="9b461-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="9b461-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="9b461-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="9b461-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-188">16400</span><span class="sxs-lookup"><span data-stu-id="9b461-188">16400</span></span></p></td>
<td><p><span data-ttu-id="9b461-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="9b461-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="9b461-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="9b461-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-191">16401</span><span class="sxs-lookup"><span data-stu-id="9b461-191">16401</span></span></p></td>
<td><p><span data-ttu-id="9b461-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="9b461-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="9b461-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="9b461-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-194">16402</span><span class="sxs-lookup"><span data-stu-id="9b461-194">16402</span></span></p></td>
<td><p><span data-ttu-id="9b461-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="9b461-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="9b461-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="9b461-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-197">16403</span><span class="sxs-lookup"><span data-stu-id="9b461-197">16403</span></span></p></td>
<td><p><span data-ttu-id="9b461-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="9b461-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="9b461-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="9b461-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-200">16404</span><span class="sxs-lookup"><span data-stu-id="9b461-200">16404</span></span></p></td>
<td><p><span data-ttu-id="9b461-201">個人電腦</span><span class="sxs-lookup"><span data-stu-id="9b461-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="9b461-202">個人電腦</span><span class="sxs-lookup"><span data-stu-id="9b461-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-203">16405</span><span class="sxs-lookup"><span data-stu-id="9b461-203">16405</span></span></p></td>
<td><p><span data-ttu-id="9b461-204">LWA</span><span class="sxs-lookup"><span data-stu-id="9b461-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="9b461-205">LWA</span><span class="sxs-lookup"><span data-stu-id="9b461-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-206">16406</span><span class="sxs-lookup"><span data-stu-id="9b461-206">16406</span></span></p></td>
<td><p><span data-ttu-id="9b461-207">OWA</span><span class="sxs-lookup"><span data-stu-id="9b461-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="9b461-208">OWA</span><span class="sxs-lookup"><span data-stu-id="9b461-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-209">16407</span><span class="sxs-lookup"><span data-stu-id="9b461-209">16407</span></span></p></td>
<td><p><span data-ttu-id="9b461-210">Aoc</span><span class="sxs-lookup"><span data-stu-id="9b461-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="9b461-211">Aoc</span><span class="sxs-lookup"><span data-stu-id="9b461-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-212">16408</span><span class="sxs-lookup"><span data-stu-id="9b461-212">16408</span></span></p></td>
<td><p><span data-ttu-id="9b461-213">GCC</span><span class="sxs-lookup"><span data-stu-id="9b461-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="9b461-214">GCC</span><span class="sxs-lookup"><span data-stu-id="9b461-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-215">16409</span><span class="sxs-lookup"><span data-stu-id="9b461-215">16409</span></span></p></td>
<td><p><span data-ttu-id="9b461-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="9b461-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="9b461-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="9b461-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-218">16410</span><span class="sxs-lookup"><span data-stu-id="9b461-218">16410</span></span></p></td>
<td><p><span data-ttu-id="9b461-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="9b461-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="9b461-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="9b461-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b461-221">32769</span><span class="sxs-lookup"><span data-stu-id="9b461-221">32769</span></span></p></td>
<td><p><span data-ttu-id="9b461-222">閘道</span><span class="sxs-lookup"><span data-stu-id="9b461-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="9b461-223">閘道</span><span class="sxs-lookup"><span data-stu-id="9b461-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b461-224">32770</span><span class="sxs-lookup"><span data-stu-id="9b461-224">32770</span></span></p></td>
<td><p><span data-ttu-id="9b461-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="9b461-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="9b461-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="9b461-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

