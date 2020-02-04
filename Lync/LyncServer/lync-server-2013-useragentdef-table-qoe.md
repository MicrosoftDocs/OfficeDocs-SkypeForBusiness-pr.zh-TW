---
title: Lync Server 2013： UserAgentDef table （QoE）
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
ms.openlocfilehash: 146c22b77ac6d2681c1844feade86242e1fcd72f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="71cfe-102">Lync Server 2013 中的 UserAgentDef table （QoE）</span><span class="sxs-lookup"><span data-stu-id="71cfe-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71cfe-103">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="71cfe-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="71cfe-104">UserAgentDef 表格會將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="71cfe-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="71cfe-105">使用者代理是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="71cfe-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71cfe-106">UAType</span><span class="sxs-lookup"><span data-stu-id="71cfe-106">UAType</span></span></th>
<th><span data-ttu-id="71cfe-107">UAName</span><span class="sxs-lookup"><span data-stu-id="71cfe-107">UAName</span></span></th>
<th><span data-ttu-id="71cfe-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="71cfe-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-109">1</span><span class="sxs-lookup"><span data-stu-id="71cfe-109">1</span></span></p></td>
<td><p><span data-ttu-id="71cfe-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="71cfe-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="71cfe-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="71cfe-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-112">2</span><span class="sxs-lookup"><span data-stu-id="71cfe-112">2</span></span></p></td>
<td><p><span data-ttu-id="71cfe-113">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="71cfe-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="71cfe-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="71cfe-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-115">4</span><span class="sxs-lookup"><span data-stu-id="71cfe-115">4</span></span></p></td>
<td><p><span data-ttu-id="71cfe-116">OC</span><span class="sxs-lookup"><span data-stu-id="71cfe-116">OC</span></span></p></td>
<td><p><span data-ttu-id="71cfe-117">OC</span><span class="sxs-lookup"><span data-stu-id="71cfe-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-118">型</span><span class="sxs-lookup"><span data-stu-id="71cfe-118">8</span></span></p></td>
<td><p><span data-ttu-id="71cfe-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="71cfe-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="71cfe-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="71cfe-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-121">位</span><span class="sxs-lookup"><span data-stu-id="71cfe-121">16</span></span></p></td>
<td><p><span data-ttu-id="71cfe-122">LMC</span><span class="sxs-lookup"><span data-stu-id="71cfe-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="71cfe-123">LMC</span><span class="sxs-lookup"><span data-stu-id="71cfe-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-124">32</span><span class="sxs-lookup"><span data-stu-id="71cfe-124">32</span></span></p></td>
<td><p><span data-ttu-id="71cfe-125">DVT</span><span class="sxs-lookup"><span data-stu-id="71cfe-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="71cfe-126">DVT</span><span class="sxs-lookup"><span data-stu-id="71cfe-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-127">64</span><span class="sxs-lookup"><span data-stu-id="71cfe-127">64</span></span></p></td>
<td><p><span data-ttu-id="71cfe-128">年</span><span class="sxs-lookup"><span data-stu-id="71cfe-128">MM</span></span></p></td>
<td><p><span data-ttu-id="71cfe-129">年</span><span class="sxs-lookup"><span data-stu-id="71cfe-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-130">64</span><span class="sxs-lookup"><span data-stu-id="71cfe-130">64</span></span></p></td>
<td><p><span data-ttu-id="71cfe-131">MC</span><span class="sxs-lookup"><span data-stu-id="71cfe-131">MC</span></span></p></td>
<td><p><span data-ttu-id="71cfe-132">年</span><span class="sxs-lookup"><span data-stu-id="71cfe-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-133">128</span><span class="sxs-lookup"><span data-stu-id="71cfe-133">128</span></span></p></td>
<td><p><span data-ttu-id="71cfe-134">值守</span><span class="sxs-lookup"><span data-stu-id="71cfe-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="71cfe-135">值守</span><span class="sxs-lookup"><span data-stu-id="71cfe-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-136">256</span><span class="sxs-lookup"><span data-stu-id="71cfe-136">256</span></span></p></td>
<td><p><span data-ttu-id="71cfe-137">Conferencing_Announcement_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="71cfe-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="71cfe-138">頒發</span><span class="sxs-lookup"><span data-stu-id="71cfe-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-139">512</span><span class="sxs-lookup"><span data-stu-id="71cfe-139">512</span></span></p></td>
<td><p><span data-ttu-id="71cfe-140">Conferencing_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="71cfe-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="71cfe-141">CAA</span><span class="sxs-lookup"><span data-stu-id="71cfe-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-142">512</span><span class="sxs-lookup"><span data-stu-id="71cfe-142">512</span></span></p></td>
<td><p><span data-ttu-id="71cfe-143">Conference_Auto_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="71cfe-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="71cfe-144">CAA</span><span class="sxs-lookup"><span data-stu-id="71cfe-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-145">1024</span><span class="sxs-lookup"><span data-stu-id="71cfe-145">1024</span></span></p></td>
<td><p><span data-ttu-id="71cfe-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="71cfe-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="71cfe-147">RG</span><span class="sxs-lookup"><span data-stu-id="71cfe-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-148">1032</span><span class="sxs-lookup"><span data-stu-id="71cfe-148">1032</span></span></p></td>
<td><p><span data-ttu-id="71cfe-149">Call_Park_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="71cfe-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="71cfe-150">CPS</span><span class="sxs-lookup"><span data-stu-id="71cfe-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-151">1040</span><span class="sxs-lookup"><span data-stu-id="71cfe-151">1040</span></span></p></td>
<td><p><span data-ttu-id="71cfe-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="71cfe-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="71cfe-153">完工</span><span class="sxs-lookup"><span data-stu-id="71cfe-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-154">2048</span><span class="sxs-lookup"><span data-stu-id="71cfe-154">2048</span></span></p></td>
<td><p><span data-ttu-id="71cfe-155">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="71cfe-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="71cfe-156">CCS</span><span class="sxs-lookup"><span data-stu-id="71cfe-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-157">16386</span><span class="sxs-lookup"><span data-stu-id="71cfe-157">16386</span></span></p></td>
<td><p><span data-ttu-id="71cfe-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="71cfe-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="71cfe-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="71cfe-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-160">16387</span><span class="sxs-lookup"><span data-stu-id="71cfe-160">16387</span></span></p></td>
<td><p><span data-ttu-id="71cfe-161">CWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="71cfe-162">CWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-163">16388</span><span class="sxs-lookup"><span data-stu-id="71cfe-163">16388</span></span></p></td>
<td><p><span data-ttu-id="71cfe-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="71cfe-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="71cfe-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="71cfe-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-166">16389</span><span class="sxs-lookup"><span data-stu-id="71cfe-166">16389</span></span></p></td>
<td><p><span data-ttu-id="71cfe-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="71cfe-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="71cfe-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="71cfe-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-169">16393</span><span class="sxs-lookup"><span data-stu-id="71cfe-169">16393</span></span></p></td>
<td><p><span data-ttu-id="71cfe-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="71cfe-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="71cfe-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="71cfe-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-172">16395</span><span class="sxs-lookup"><span data-stu-id="71cfe-172">16395</span></span></p></td>
<td><p><span data-ttu-id="71cfe-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="71cfe-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="71cfe-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="71cfe-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-175">16396</span><span class="sxs-lookup"><span data-stu-id="71cfe-175">16396</span></span></p></td>
<td><p><span data-ttu-id="71cfe-176">短期</span><span class="sxs-lookup"><span data-stu-id="71cfe-176">ST</span></span></p></td>
<td><p><span data-ttu-id="71cfe-177">短期</span><span class="sxs-lookup"><span data-stu-id="71cfe-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-178">16397</span><span class="sxs-lookup"><span data-stu-id="71cfe-178">16397</span></span></p></td>
<td><p><span data-ttu-id="71cfe-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="71cfe-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="71cfe-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="71cfe-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-181">16398</span><span class="sxs-lookup"><span data-stu-id="71cfe-181">16398</span></span></p></td>
<td><p><span data-ttu-id="71cfe-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="71cfe-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-184">16399</span><span class="sxs-lookup"><span data-stu-id="71cfe-184">16399</span></span></p></td>
<td><p><span data-ttu-id="71cfe-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="71cfe-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-187">16400</span><span class="sxs-lookup"><span data-stu-id="71cfe-187">16400</span></span></p></td>
<td><p><span data-ttu-id="71cfe-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="71cfe-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-190">16401</span><span class="sxs-lookup"><span data-stu-id="71cfe-190">16401</span></span></p></td>
<td><p><span data-ttu-id="71cfe-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="71cfe-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-193">16402</span><span class="sxs-lookup"><span data-stu-id="71cfe-193">16402</span></span></p></td>
<td><p><span data-ttu-id="71cfe-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="71cfe-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="71cfe-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-196">16403</span><span class="sxs-lookup"><span data-stu-id="71cfe-196">16403</span></span></p></td>
<td><p><span data-ttu-id="71cfe-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="71cfe-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="71cfe-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="71cfe-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-199">16404</span><span class="sxs-lookup"><span data-stu-id="71cfe-199">16404</span></span></p></td>
<td><p><span data-ttu-id="71cfe-200">買</span><span class="sxs-lookup"><span data-stu-id="71cfe-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="71cfe-201">買</span><span class="sxs-lookup"><span data-stu-id="71cfe-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-202">16405</span><span class="sxs-lookup"><span data-stu-id="71cfe-202">16405</span></span></p></td>
<td><p><span data-ttu-id="71cfe-203">LWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="71cfe-204">LWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-205">16406</span><span class="sxs-lookup"><span data-stu-id="71cfe-205">16406</span></span></p></td>
<td><p><span data-ttu-id="71cfe-206">OWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="71cfe-207">OWA</span><span class="sxs-lookup"><span data-stu-id="71cfe-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-208">16407</span><span class="sxs-lookup"><span data-stu-id="71cfe-208">16407</span></span></p></td>
<td><p><span data-ttu-id="71cfe-209">AOC</span><span class="sxs-lookup"><span data-stu-id="71cfe-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="71cfe-210">AOC</span><span class="sxs-lookup"><span data-stu-id="71cfe-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-211">16408</span><span class="sxs-lookup"><span data-stu-id="71cfe-211">16408</span></span></p></td>
<td><p><span data-ttu-id="71cfe-212">GCC</span><span class="sxs-lookup"><span data-stu-id="71cfe-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="71cfe-213">GCC</span><span class="sxs-lookup"><span data-stu-id="71cfe-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-214">16409</span><span class="sxs-lookup"><span data-stu-id="71cfe-214">16409</span></span></p></td>
<td><p><span data-ttu-id="71cfe-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="71cfe-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="71cfe-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="71cfe-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-217">16410</span><span class="sxs-lookup"><span data-stu-id="71cfe-217">16410</span></span></p></td>
<td><p><span data-ttu-id="71cfe-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="71cfe-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="71cfe-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="71cfe-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71cfe-220">32769</span><span class="sxs-lookup"><span data-stu-id="71cfe-220">32769</span></span></p></td>
<td><p><span data-ttu-id="71cfe-221">關</span><span class="sxs-lookup"><span data-stu-id="71cfe-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="71cfe-222">關</span><span class="sxs-lookup"><span data-stu-id="71cfe-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71cfe-223">32770</span><span class="sxs-lookup"><span data-stu-id="71cfe-223">32770</span></span></p></td>
<td><p><span data-ttu-id="71cfe-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="71cfe-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="71cfe-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="71cfe-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

