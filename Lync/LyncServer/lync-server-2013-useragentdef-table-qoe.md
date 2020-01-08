---
title: Lync Server 2013： UserAgentDef table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgentDef table (QoE)
ms:assetid: cfd8e3e0-4076-4162-9381-5276da8316d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205259(v=OCS.15)
ms:contentKeyID: 48185394
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adfe05a24d2a45cf5d6d279b29d77b1c7654012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="9e53a-102">Lync Server 2013 中的 UserAgentDef table （QoE）</span><span class="sxs-lookup"><span data-stu-id="9e53a-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e53a-103">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="9e53a-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="9e53a-104">UserAgentDef 表格會將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="9e53a-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="9e53a-105">使用者代理是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="9e53a-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e53a-106">UAType</span><span class="sxs-lookup"><span data-stu-id="9e53a-106">UAType</span></span></th>
<th><span data-ttu-id="9e53a-107">UAName</span><span class="sxs-lookup"><span data-stu-id="9e53a-107">UAName</span></span></th>
<th><span data-ttu-id="9e53a-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="9e53a-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-109">1</span><span class="sxs-lookup"><span data-stu-id="9e53a-109">1</span></span></p></td>
<td><p><span data-ttu-id="9e53a-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="9e53a-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="9e53a-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="9e53a-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-112">pplx-2</span><span class="sxs-lookup"><span data-stu-id="9e53a-112">2</span></span></p></td>
<td><p><span data-ttu-id="9e53a-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="9e53a-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="9e53a-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="9e53a-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-115">4</span><span class="sxs-lookup"><span data-stu-id="9e53a-115">4</span></span></p></td>
<td><p><span data-ttu-id="9e53a-116">OC</span><span class="sxs-lookup"><span data-stu-id="9e53a-116">OC</span></span></p></td>
<td><p><span data-ttu-id="9e53a-117">OC</span><span class="sxs-lookup"><span data-stu-id="9e53a-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-118">型</span><span class="sxs-lookup"><span data-stu-id="9e53a-118">8</span></span></p></td>
<td><p><span data-ttu-id="9e53a-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9e53a-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="9e53a-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9e53a-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-121">位</span><span class="sxs-lookup"><span data-stu-id="9e53a-121">16</span></span></p></td>
<td><p><span data-ttu-id="9e53a-122">LMC</span><span class="sxs-lookup"><span data-stu-id="9e53a-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="9e53a-123">LMC</span><span class="sxs-lookup"><span data-stu-id="9e53a-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-124">32</span><span class="sxs-lookup"><span data-stu-id="9e53a-124">32</span></span></p></td>
<td><p><span data-ttu-id="9e53a-125">DVT</span><span class="sxs-lookup"><span data-stu-id="9e53a-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="9e53a-126">DVT</span><span class="sxs-lookup"><span data-stu-id="9e53a-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-127">64</span><span class="sxs-lookup"><span data-stu-id="9e53a-127">64</span></span></p></td>
<td><p><span data-ttu-id="9e53a-128">年</span><span class="sxs-lookup"><span data-stu-id="9e53a-128">MM</span></span></p></td>
<td><p><span data-ttu-id="9e53a-129">年</span><span class="sxs-lookup"><span data-stu-id="9e53a-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-130">64</span><span class="sxs-lookup"><span data-stu-id="9e53a-130">64</span></span></p></td>
<td><p><span data-ttu-id="9e53a-131">MC</span><span class="sxs-lookup"><span data-stu-id="9e53a-131">MC</span></span></p></td>
<td><p><span data-ttu-id="9e53a-132">年</span><span class="sxs-lookup"><span data-stu-id="9e53a-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-133">128</span><span class="sxs-lookup"><span data-stu-id="9e53a-133">128</span></span></p></td>
<td><p><span data-ttu-id="9e53a-134">值守</span><span class="sxs-lookup"><span data-stu-id="9e53a-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="9e53a-135">值守</span><span class="sxs-lookup"><span data-stu-id="9e53a-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-136">256</span><span class="sxs-lookup"><span data-stu-id="9e53a-136">256</span></span></p></td>
<td><p><span data-ttu-id="9e53a-137">Conferencing_Announcement_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="9e53a-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="9e53a-138">頒發</span><span class="sxs-lookup"><span data-stu-id="9e53a-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-139">512</span><span class="sxs-lookup"><span data-stu-id="9e53a-139">512</span></span></p></td>
<td><p><span data-ttu-id="9e53a-140">Conferencing_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="9e53a-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="9e53a-141">CAA</span><span class="sxs-lookup"><span data-stu-id="9e53a-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-142">512</span><span class="sxs-lookup"><span data-stu-id="9e53a-142">512</span></span></p></td>
<td><p><span data-ttu-id="9e53a-143">Conference_Auto_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="9e53a-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="9e53a-144">CAA</span><span class="sxs-lookup"><span data-stu-id="9e53a-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-145">1024</span><span class="sxs-lookup"><span data-stu-id="9e53a-145">1024</span></span></p></td>
<td><p><span data-ttu-id="9e53a-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="9e53a-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="9e53a-147">RG</span><span class="sxs-lookup"><span data-stu-id="9e53a-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-148">1032</span><span class="sxs-lookup"><span data-stu-id="9e53a-148">1032</span></span></p></td>
<td><p><span data-ttu-id="9e53a-149">Call_Park_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="9e53a-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="9e53a-150">CPS</span><span class="sxs-lookup"><span data-stu-id="9e53a-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-151">1040</span><span class="sxs-lookup"><span data-stu-id="9e53a-151">1040</span></span></p></td>
<td><p><span data-ttu-id="9e53a-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="9e53a-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="9e53a-153">完工</span><span class="sxs-lookup"><span data-stu-id="9e53a-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-154">2048</span><span class="sxs-lookup"><span data-stu-id="9e53a-154">2048</span></span></p></td>
<td><p><span data-ttu-id="9e53a-155">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="9e53a-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="9e53a-156">CCS</span><span class="sxs-lookup"><span data-stu-id="9e53a-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-157">16386</span><span class="sxs-lookup"><span data-stu-id="9e53a-157">16386</span></span></p></td>
<td><p><span data-ttu-id="9e53a-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="9e53a-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="9e53a-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="9e53a-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-160">16387</span><span class="sxs-lookup"><span data-stu-id="9e53a-160">16387</span></span></p></td>
<td><p><span data-ttu-id="9e53a-161">CWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="9e53a-162">CWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-163">16388</span><span class="sxs-lookup"><span data-stu-id="9e53a-163">16388</span></span></p></td>
<td><p><span data-ttu-id="9e53a-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="9e53a-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="9e53a-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="9e53a-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-166">16389</span><span class="sxs-lookup"><span data-stu-id="9e53a-166">16389</span></span></p></td>
<td><p><span data-ttu-id="9e53a-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="9e53a-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="9e53a-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="9e53a-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-169">16393</span><span class="sxs-lookup"><span data-stu-id="9e53a-169">16393</span></span></p></td>
<td><p><span data-ttu-id="9e53a-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="9e53a-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="9e53a-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="9e53a-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-172">16395</span><span class="sxs-lookup"><span data-stu-id="9e53a-172">16395</span></span></p></td>
<td><p><span data-ttu-id="9e53a-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="9e53a-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="9e53a-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="9e53a-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-175">16396</span><span class="sxs-lookup"><span data-stu-id="9e53a-175">16396</span></span></p></td>
<td><p><span data-ttu-id="9e53a-176">短期</span><span class="sxs-lookup"><span data-stu-id="9e53a-176">ST</span></span></p></td>
<td><p><span data-ttu-id="9e53a-177">短期</span><span class="sxs-lookup"><span data-stu-id="9e53a-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-178">16397</span><span class="sxs-lookup"><span data-stu-id="9e53a-178">16397</span></span></p></td>
<td><p><span data-ttu-id="9e53a-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="9e53a-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="9e53a-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="9e53a-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-181">16398</span><span class="sxs-lookup"><span data-stu-id="9e53a-181">16398</span></span></p></td>
<td><p><span data-ttu-id="9e53a-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="9e53a-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-184">16399</span><span class="sxs-lookup"><span data-stu-id="9e53a-184">16399</span></span></p></td>
<td><p><span data-ttu-id="9e53a-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="9e53a-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-187">16400</span><span class="sxs-lookup"><span data-stu-id="9e53a-187">16400</span></span></p></td>
<td><p><span data-ttu-id="9e53a-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="9e53a-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-190">16401</span><span class="sxs-lookup"><span data-stu-id="9e53a-190">16401</span></span></p></td>
<td><p><span data-ttu-id="9e53a-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="9e53a-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-193">16402</span><span class="sxs-lookup"><span data-stu-id="9e53a-193">16402</span></span></p></td>
<td><p><span data-ttu-id="9e53a-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="9e53a-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="9e53a-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-196">16403</span><span class="sxs-lookup"><span data-stu-id="9e53a-196">16403</span></span></p></td>
<td><p><span data-ttu-id="9e53a-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="9e53a-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="9e53a-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="9e53a-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-199">16404</span><span class="sxs-lookup"><span data-stu-id="9e53a-199">16404</span></span></p></td>
<td><p><span data-ttu-id="9e53a-200">買</span><span class="sxs-lookup"><span data-stu-id="9e53a-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="9e53a-201">買</span><span class="sxs-lookup"><span data-stu-id="9e53a-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-202">16405</span><span class="sxs-lookup"><span data-stu-id="9e53a-202">16405</span></span></p></td>
<td><p><span data-ttu-id="9e53a-203">LWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="9e53a-204">LWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-205">16406</span><span class="sxs-lookup"><span data-stu-id="9e53a-205">16406</span></span></p></td>
<td><p><span data-ttu-id="9e53a-206">OWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="9e53a-207">OWA</span><span class="sxs-lookup"><span data-stu-id="9e53a-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-208">16407</span><span class="sxs-lookup"><span data-stu-id="9e53a-208">16407</span></span></p></td>
<td><p><span data-ttu-id="9e53a-209">AOC</span><span class="sxs-lookup"><span data-stu-id="9e53a-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="9e53a-210">AOC</span><span class="sxs-lookup"><span data-stu-id="9e53a-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-211">16408</span><span class="sxs-lookup"><span data-stu-id="9e53a-211">16408</span></span></p></td>
<td><p><span data-ttu-id="9e53a-212">GCC</span><span class="sxs-lookup"><span data-stu-id="9e53a-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="9e53a-213">GCC</span><span class="sxs-lookup"><span data-stu-id="9e53a-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-214">16409</span><span class="sxs-lookup"><span data-stu-id="9e53a-214">16409</span></span></p></td>
<td><p><span data-ttu-id="9e53a-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="9e53a-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="9e53a-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="9e53a-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-217">16410</span><span class="sxs-lookup"><span data-stu-id="9e53a-217">16410</span></span></p></td>
<td><p><span data-ttu-id="9e53a-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="9e53a-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="9e53a-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="9e53a-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e53a-220">32769</span><span class="sxs-lookup"><span data-stu-id="9e53a-220">32769</span></span></p></td>
<td><p><span data-ttu-id="9e53a-221">關</span><span class="sxs-lookup"><span data-stu-id="9e53a-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="9e53a-222">關</span><span class="sxs-lookup"><span data-stu-id="9e53a-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e53a-223">32770</span><span class="sxs-lookup"><span data-stu-id="9e53a-223">32770</span></span></p></td>
<td><p><span data-ttu-id="9e53a-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="9e53a-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="9e53a-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="9e53a-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

