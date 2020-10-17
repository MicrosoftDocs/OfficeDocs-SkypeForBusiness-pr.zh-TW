---
title: 'Lync Server 2013： UserAgentDef table (QoE) '
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
ms.openlocfilehash: 7294c70a0ebfd49f954bbe911d2fccb81d79fa54
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530100"
---
# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="63d8e-102">在 Lync Server 2013 中 UserAgentDef table (QoE) </span><span class="sxs-lookup"><span data-stu-id="63d8e-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63d8e-103">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="63d8e-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="63d8e-104">UserAgentDef 表會將使用者代理程式識別碼對應到代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="63d8e-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="63d8e-105">使用者代理程式是用來連接至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="63d8e-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63d8e-106">UAType</span><span class="sxs-lookup"><span data-stu-id="63d8e-106">UAType</span></span></th>
<th><span data-ttu-id="63d8e-107">UAName</span><span class="sxs-lookup"><span data-stu-id="63d8e-107">UAName</span></span></th>
<th><span data-ttu-id="63d8e-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="63d8e-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-109">1 </span><span class="sxs-lookup"><span data-stu-id="63d8e-109">1</span></span></p></td>
<td><p><span data-ttu-id="63d8e-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="63d8e-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="63d8e-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="63d8e-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-112">第</span><span class="sxs-lookup"><span data-stu-id="63d8e-112">2</span></span></p></td>
<td><p><span data-ttu-id="63d8e-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="63d8e-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="63d8e-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="63d8e-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-115">4 </span><span class="sxs-lookup"><span data-stu-id="63d8e-115">4</span></span></p></td>
<td><p><span data-ttu-id="63d8e-116">Oc</span><span class="sxs-lookup"><span data-stu-id="63d8e-116">OC</span></span></p></td>
<td><p><span data-ttu-id="63d8e-117">Oc</span><span class="sxs-lookup"><span data-stu-id="63d8e-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-118">8 </span><span class="sxs-lookup"><span data-stu-id="63d8e-118">8</span></span></p></td>
<td><p><span data-ttu-id="63d8e-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="63d8e-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="63d8e-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="63d8e-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-121">16 </span><span class="sxs-lookup"><span data-stu-id="63d8e-121">16</span></span></p></td>
<td><p><span data-ttu-id="63d8e-122">LMC</span><span class="sxs-lookup"><span data-stu-id="63d8e-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="63d8e-123">LMC</span><span class="sxs-lookup"><span data-stu-id="63d8e-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-124">32</span><span class="sxs-lookup"><span data-stu-id="63d8e-124">32</span></span></p></td>
<td><p><span data-ttu-id="63d8e-125">Dvt</span><span class="sxs-lookup"><span data-stu-id="63d8e-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="63d8e-126">Dvt</span><span class="sxs-lookup"><span data-stu-id="63d8e-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-127">64</span><span class="sxs-lookup"><span data-stu-id="63d8e-127">64</span></span></p></td>
<td><p><span data-ttu-id="63d8e-128">毫米</span><span class="sxs-lookup"><span data-stu-id="63d8e-128">MM</span></span></p></td>
<td><p><span data-ttu-id="63d8e-129">毫米</span><span class="sxs-lookup"><span data-stu-id="63d8e-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-130">64</span><span class="sxs-lookup"><span data-stu-id="63d8e-130">64</span></span></p></td>
<td><p><span data-ttu-id="63d8e-131">Mc</span><span class="sxs-lookup"><span data-stu-id="63d8e-131">MC</span></span></p></td>
<td><p><span data-ttu-id="63d8e-132">毫米</span><span class="sxs-lookup"><span data-stu-id="63d8e-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-133">128</span><span class="sxs-lookup"><span data-stu-id="63d8e-133">128</span></span></p></td>
<td><p><span data-ttu-id="63d8e-134">語音應答</span><span class="sxs-lookup"><span data-stu-id="63d8e-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="63d8e-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="63d8e-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-136">256</span><span class="sxs-lookup"><span data-stu-id="63d8e-136">256</span></span></p></td>
<td><p><span data-ttu-id="63d8e-137">Conferencing_Announcement_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="63d8e-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="63d8e-138">Cas</span><span class="sxs-lookup"><span data-stu-id="63d8e-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-139">512</span><span class="sxs-lookup"><span data-stu-id="63d8e-139">512</span></span></p></td>
<td><p><span data-ttu-id="63d8e-140">Conferencing_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="63d8e-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="63d8e-141">Caa</span><span class="sxs-lookup"><span data-stu-id="63d8e-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-142">512</span><span class="sxs-lookup"><span data-stu-id="63d8e-142">512</span></span></p></td>
<td><p><span data-ttu-id="63d8e-143">Conference_Auto_Attendant_1。0</span><span class="sxs-lookup"><span data-stu-id="63d8e-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="63d8e-144">Caa</span><span class="sxs-lookup"><span data-stu-id="63d8e-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-145">1024</span><span class="sxs-lookup"><span data-stu-id="63d8e-145">1024</span></span></p></td>
<td><p><span data-ttu-id="63d8e-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="63d8e-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="63d8e-147">RG</span><span class="sxs-lookup"><span data-stu-id="63d8e-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-148">1032</span><span class="sxs-lookup"><span data-stu-id="63d8e-148">1032</span></span></p></td>
<td><p><span data-ttu-id="63d8e-149">Call_Park_Service_1。0</span><span class="sxs-lookup"><span data-stu-id="63d8e-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="63d8e-150">Cps</span><span class="sxs-lookup"><span data-stu-id="63d8e-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-151">1040</span><span class="sxs-lookup"><span data-stu-id="63d8e-151">1040</span></span></p></td>
<td><p><span data-ttu-id="63d8e-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="63d8e-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="63d8e-153">AS</span><span class="sxs-lookup"><span data-stu-id="63d8e-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-154">2048</span><span class="sxs-lookup"><span data-stu-id="63d8e-154">2048</span></span></p></td>
<td><p><span data-ttu-id="63d8e-155">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="63d8e-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="63d8e-156">Ccs</span><span class="sxs-lookup"><span data-stu-id="63d8e-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-157">16386</span><span class="sxs-lookup"><span data-stu-id="63d8e-157">16386</span></span></p></td>
<td><p><span data-ttu-id="63d8e-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="63d8e-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="63d8e-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="63d8e-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-160">16387</span><span class="sxs-lookup"><span data-stu-id="63d8e-160">16387</span></span></p></td>
<td><p><span data-ttu-id="63d8e-161">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="63d8e-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="63d8e-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="63d8e-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-163">16388</span><span class="sxs-lookup"><span data-stu-id="63d8e-163">16388</span></span></p></td>
<td><p><span data-ttu-id="63d8e-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="63d8e-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="63d8e-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="63d8e-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-166">16389</span><span class="sxs-lookup"><span data-stu-id="63d8e-166">16389</span></span></p></td>
<td><p><span data-ttu-id="63d8e-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="63d8e-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="63d8e-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="63d8e-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-169">16393</span><span class="sxs-lookup"><span data-stu-id="63d8e-169">16393</span></span></p></td>
<td><p><span data-ttu-id="63d8e-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="63d8e-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="63d8e-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="63d8e-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-172">16395</span><span class="sxs-lookup"><span data-stu-id="63d8e-172">16395</span></span></p></td>
<td><p><span data-ttu-id="63d8e-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="63d8e-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="63d8e-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="63d8e-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-175">16396</span><span class="sxs-lookup"><span data-stu-id="63d8e-175">16396</span></span></p></td>
<td><p><span data-ttu-id="63d8e-176">聖</span><span class="sxs-lookup"><span data-stu-id="63d8e-176">ST</span></span></p></td>
<td><p><span data-ttu-id="63d8e-177">聖</span><span class="sxs-lookup"><span data-stu-id="63d8e-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-178">16397</span><span class="sxs-lookup"><span data-stu-id="63d8e-178">16397</span></span></p></td>
<td><p><span data-ttu-id="63d8e-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="63d8e-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="63d8e-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="63d8e-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-181">16398</span><span class="sxs-lookup"><span data-stu-id="63d8e-181">16398</span></span></p></td>
<td><p><span data-ttu-id="63d8e-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="63d8e-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-184">16399</span><span class="sxs-lookup"><span data-stu-id="63d8e-184">16399</span></span></p></td>
<td><p><span data-ttu-id="63d8e-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="63d8e-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-187">16400</span><span class="sxs-lookup"><span data-stu-id="63d8e-187">16400</span></span></p></td>
<td><p><span data-ttu-id="63d8e-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="63d8e-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-190">16401</span><span class="sxs-lookup"><span data-stu-id="63d8e-190">16401</span></span></p></td>
<td><p><span data-ttu-id="63d8e-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="63d8e-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-193">16402</span><span class="sxs-lookup"><span data-stu-id="63d8e-193">16402</span></span></p></td>
<td><p><span data-ttu-id="63d8e-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="63d8e-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="63d8e-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-196">16403</span><span class="sxs-lookup"><span data-stu-id="63d8e-196">16403</span></span></p></td>
<td><p><span data-ttu-id="63d8e-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="63d8e-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="63d8e-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="63d8e-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-199">16404</span><span class="sxs-lookup"><span data-stu-id="63d8e-199">16404</span></span></p></td>
<td><p><span data-ttu-id="63d8e-200">個人電腦</span><span class="sxs-lookup"><span data-stu-id="63d8e-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="63d8e-201">個人電腦</span><span class="sxs-lookup"><span data-stu-id="63d8e-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-202">16405</span><span class="sxs-lookup"><span data-stu-id="63d8e-202">16405</span></span></p></td>
<td><p><span data-ttu-id="63d8e-203">LWA</span><span class="sxs-lookup"><span data-stu-id="63d8e-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="63d8e-204">LWA</span><span class="sxs-lookup"><span data-stu-id="63d8e-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-205">16406</span><span class="sxs-lookup"><span data-stu-id="63d8e-205">16406</span></span></p></td>
<td><p><span data-ttu-id="63d8e-206">OWA</span><span class="sxs-lookup"><span data-stu-id="63d8e-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="63d8e-207">OWA</span><span class="sxs-lookup"><span data-stu-id="63d8e-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-208">16407</span><span class="sxs-lookup"><span data-stu-id="63d8e-208">16407</span></span></p></td>
<td><p><span data-ttu-id="63d8e-209">Aoc</span><span class="sxs-lookup"><span data-stu-id="63d8e-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="63d8e-210">Aoc</span><span class="sxs-lookup"><span data-stu-id="63d8e-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-211">16408</span><span class="sxs-lookup"><span data-stu-id="63d8e-211">16408</span></span></p></td>
<td><p><span data-ttu-id="63d8e-212">GCC</span><span class="sxs-lookup"><span data-stu-id="63d8e-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="63d8e-213">GCC</span><span class="sxs-lookup"><span data-stu-id="63d8e-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-214">16409</span><span class="sxs-lookup"><span data-stu-id="63d8e-214">16409</span></span></p></td>
<td><p><span data-ttu-id="63d8e-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="63d8e-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="63d8e-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="63d8e-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-217">16410</span><span class="sxs-lookup"><span data-stu-id="63d8e-217">16410</span></span></p></td>
<td><p><span data-ttu-id="63d8e-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="63d8e-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="63d8e-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="63d8e-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63d8e-220">32769</span><span class="sxs-lookup"><span data-stu-id="63d8e-220">32769</span></span></p></td>
<td><p><span data-ttu-id="63d8e-221">閘道</span><span class="sxs-lookup"><span data-stu-id="63d8e-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="63d8e-222">閘道</span><span class="sxs-lookup"><span data-stu-id="63d8e-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63d8e-223">32770</span><span class="sxs-lookup"><span data-stu-id="63d8e-223">32770</span></span></p></td>
<td><p><span data-ttu-id="63d8e-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="63d8e-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="63d8e-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="63d8e-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

