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
ms.openlocfilehash: 952f065c5377a4d4e94677f9088569ffca681151
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="f12c4-102">Lync Server 2013 中的 UserAgentDef 表格</span><span class="sxs-lookup"><span data-stu-id="f12c4-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f12c4-103">_**主題上次修改日期：** 2014-03-25_</span><span class="sxs-lookup"><span data-stu-id="f12c4-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="f12c4-104">UserAgentDef 表格會將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="f12c4-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="f12c4-105">使用者代理是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="f12c4-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f12c4-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="f12c4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f12c4-107">UAType</span><span class="sxs-lookup"><span data-stu-id="f12c4-107">UAType</span></span></th>
<th><span data-ttu-id="f12c4-108">UAName</span><span class="sxs-lookup"><span data-stu-id="f12c4-108">UAName</span></span></th>
<th><span data-ttu-id="f12c4-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="f12c4-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-110">1</span><span class="sxs-lookup"><span data-stu-id="f12c4-110">1</span></span></p></td>
<td><p><span data-ttu-id="f12c4-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="f12c4-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="f12c4-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="f12c4-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-113">2</span><span class="sxs-lookup"><span data-stu-id="f12c4-113">2</span></span></p></td>
<td><p><span data-ttu-id="f12c4-114">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="f12c4-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="f12c4-115">AV-MCU</span><span class="sxs-lookup"><span data-stu-id="f12c4-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-116">4</span><span class="sxs-lookup"><span data-stu-id="f12c4-116">4</span></span></p></td>
<td><p><span data-ttu-id="f12c4-117">OC</span><span class="sxs-lookup"><span data-stu-id="f12c4-117">OC</span></span></p></td>
<td><p><span data-ttu-id="f12c4-118">OC</span><span class="sxs-lookup"><span data-stu-id="f12c4-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-119">型</span><span class="sxs-lookup"><span data-stu-id="f12c4-119">8</span></span></p></td>
<td><p><span data-ttu-id="f12c4-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="f12c4-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="f12c4-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="f12c4-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-122">位</span><span class="sxs-lookup"><span data-stu-id="f12c4-122">16</span></span></p></td>
<td><p><span data-ttu-id="f12c4-123">LMC</span><span class="sxs-lookup"><span data-stu-id="f12c4-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="f12c4-124">LMC</span><span class="sxs-lookup"><span data-stu-id="f12c4-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-125">32</span><span class="sxs-lookup"><span data-stu-id="f12c4-125">32</span></span></p></td>
<td><p><span data-ttu-id="f12c4-126">DVT</span><span class="sxs-lookup"><span data-stu-id="f12c4-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="f12c4-127">DVT</span><span class="sxs-lookup"><span data-stu-id="f12c4-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-128">64</span><span class="sxs-lookup"><span data-stu-id="f12c4-128">64</span></span></p></td>
<td><p><span data-ttu-id="f12c4-129">年</span><span class="sxs-lookup"><span data-stu-id="f12c4-129">MM</span></span></p></td>
<td><p><span data-ttu-id="f12c4-130">年</span><span class="sxs-lookup"><span data-stu-id="f12c4-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-131">64</span><span class="sxs-lookup"><span data-stu-id="f12c4-131">64</span></span></p></td>
<td><p><span data-ttu-id="f12c4-132">MC</span><span class="sxs-lookup"><span data-stu-id="f12c4-132">MC</span></span></p></td>
<td><p><span data-ttu-id="f12c4-133">年</span><span class="sxs-lookup"><span data-stu-id="f12c4-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-134">128</span><span class="sxs-lookup"><span data-stu-id="f12c4-134">128</span></span></p></td>
<td><p><span data-ttu-id="f12c4-135">值守</span><span class="sxs-lookup"><span data-stu-id="f12c4-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="f12c4-136">值守</span><span class="sxs-lookup"><span data-stu-id="f12c4-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-137">256</span><span class="sxs-lookup"><span data-stu-id="f12c4-137">256</span></span></p></td>
<td><p><span data-ttu-id="f12c4-138">Conferencing_Announcement_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="f12c4-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="f12c4-139">頒發</span><span class="sxs-lookup"><span data-stu-id="f12c4-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-140">512</span><span class="sxs-lookup"><span data-stu-id="f12c4-140">512</span></span></p></td>
<td><p><span data-ttu-id="f12c4-141">Conferencing_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="f12c4-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="f12c4-142">CAA</span><span class="sxs-lookup"><span data-stu-id="f12c4-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-143">512</span><span class="sxs-lookup"><span data-stu-id="f12c4-143">512</span></span></p></td>
<td><p><span data-ttu-id="f12c4-144">Conference_Auto_Attendant_1. 0</span><span class="sxs-lookup"><span data-stu-id="f12c4-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="f12c4-145">CAA</span><span class="sxs-lookup"><span data-stu-id="f12c4-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-146">1024</span><span class="sxs-lookup"><span data-stu-id="f12c4-146">1024</span></span></p></td>
<td><p><span data-ttu-id="f12c4-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="f12c4-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="f12c4-148">RG</span><span class="sxs-lookup"><span data-stu-id="f12c4-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-149">1032</span><span class="sxs-lookup"><span data-stu-id="f12c4-149">1032</span></span></p></td>
<td><p><span data-ttu-id="f12c4-150">Call_Park_Service_1. 0</span><span class="sxs-lookup"><span data-stu-id="f12c4-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="f12c4-151">CPS</span><span class="sxs-lookup"><span data-stu-id="f12c4-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-152">1040</span><span class="sxs-lookup"><span data-stu-id="f12c4-152">1040</span></span></p></td>
<td><p><span data-ttu-id="f12c4-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="f12c4-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="f12c4-154">完工</span><span class="sxs-lookup"><span data-stu-id="f12c4-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-155">2048</span><span class="sxs-lookup"><span data-stu-id="f12c4-155">2048</span></span></p></td>
<td><p><span data-ttu-id="f12c4-156">Ccs 的應用程式</span><span class="sxs-lookup"><span data-stu-id="f12c4-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="f12c4-157">CCS</span><span class="sxs-lookup"><span data-stu-id="f12c4-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-158">16386</span><span class="sxs-lookup"><span data-stu-id="f12c4-158">16386</span></span></p></td>
<td><p><span data-ttu-id="f12c4-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="f12c4-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="f12c4-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="f12c4-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-161">16387</span><span class="sxs-lookup"><span data-stu-id="f12c4-161">16387</span></span></p></td>
<td><p><span data-ttu-id="f12c4-162">CWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="f12c4-163">CWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-164">16388</span><span class="sxs-lookup"><span data-stu-id="f12c4-164">16388</span></span></p></td>
<td><p><span data-ttu-id="f12c4-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="f12c4-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="f12c4-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="f12c4-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-167">16389</span><span class="sxs-lookup"><span data-stu-id="f12c4-167">16389</span></span></p></td>
<td><p><span data-ttu-id="f12c4-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="f12c4-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="f12c4-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="f12c4-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-170">16393</span><span class="sxs-lookup"><span data-stu-id="f12c4-170">16393</span></span></p></td>
<td><p><span data-ttu-id="f12c4-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="f12c4-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="f12c4-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="f12c4-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-173">16395</span><span class="sxs-lookup"><span data-stu-id="f12c4-173">16395</span></span></p></td>
<td><p><span data-ttu-id="f12c4-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="f12c4-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="f12c4-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="f12c4-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-176">16396</span><span class="sxs-lookup"><span data-stu-id="f12c4-176">16396</span></span></p></td>
<td><p><span data-ttu-id="f12c4-177">短期</span><span class="sxs-lookup"><span data-stu-id="f12c4-177">ST</span></span></p></td>
<td><p><span data-ttu-id="f12c4-178">短期</span><span class="sxs-lookup"><span data-stu-id="f12c4-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-179">16397</span><span class="sxs-lookup"><span data-stu-id="f12c4-179">16397</span></span></p></td>
<td><p><span data-ttu-id="f12c4-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="f12c4-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="f12c4-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="f12c4-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-182">16398</span><span class="sxs-lookup"><span data-stu-id="f12c4-182">16398</span></span></p></td>
<td><p><span data-ttu-id="f12c4-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="f12c4-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-185">16399</span><span class="sxs-lookup"><span data-stu-id="f12c4-185">16399</span></span></p></td>
<td><p><span data-ttu-id="f12c4-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="f12c4-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-188">16400</span><span class="sxs-lookup"><span data-stu-id="f12c4-188">16400</span></span></p></td>
<td><p><span data-ttu-id="f12c4-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="f12c4-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-191">16401</span><span class="sxs-lookup"><span data-stu-id="f12c4-191">16401</span></span></p></td>
<td><p><span data-ttu-id="f12c4-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="f12c4-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-194">16402</span><span class="sxs-lookup"><span data-stu-id="f12c4-194">16402</span></span></p></td>
<td><p><span data-ttu-id="f12c4-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="f12c4-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="f12c4-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-197">16403</span><span class="sxs-lookup"><span data-stu-id="f12c4-197">16403</span></span></p></td>
<td><p><span data-ttu-id="f12c4-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="f12c4-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="f12c4-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="f12c4-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-200">16404</span><span class="sxs-lookup"><span data-stu-id="f12c4-200">16404</span></span></p></td>
<td><p><span data-ttu-id="f12c4-201">買</span><span class="sxs-lookup"><span data-stu-id="f12c4-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="f12c4-202">買</span><span class="sxs-lookup"><span data-stu-id="f12c4-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-203">16405</span><span class="sxs-lookup"><span data-stu-id="f12c4-203">16405</span></span></p></td>
<td><p><span data-ttu-id="f12c4-204">LWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="f12c4-205">LWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-206">16406</span><span class="sxs-lookup"><span data-stu-id="f12c4-206">16406</span></span></p></td>
<td><p><span data-ttu-id="f12c4-207">OWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="f12c4-208">OWA</span><span class="sxs-lookup"><span data-stu-id="f12c4-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-209">16407</span><span class="sxs-lookup"><span data-stu-id="f12c4-209">16407</span></span></p></td>
<td><p><span data-ttu-id="f12c4-210">AOC</span><span class="sxs-lookup"><span data-stu-id="f12c4-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="f12c4-211">AOC</span><span class="sxs-lookup"><span data-stu-id="f12c4-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-212">16408</span><span class="sxs-lookup"><span data-stu-id="f12c4-212">16408</span></span></p></td>
<td><p><span data-ttu-id="f12c4-213">GCC</span><span class="sxs-lookup"><span data-stu-id="f12c4-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="f12c4-214">GCC</span><span class="sxs-lookup"><span data-stu-id="f12c4-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-215">16409</span><span class="sxs-lookup"><span data-stu-id="f12c4-215">16409</span></span></p></td>
<td><p><span data-ttu-id="f12c4-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="f12c4-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="f12c4-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="f12c4-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-218">16410</span><span class="sxs-lookup"><span data-stu-id="f12c4-218">16410</span></span></p></td>
<td><p><span data-ttu-id="f12c4-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="f12c4-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="f12c4-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="f12c4-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f12c4-221">32769</span><span class="sxs-lookup"><span data-stu-id="f12c4-221">32769</span></span></p></td>
<td><p><span data-ttu-id="f12c4-222">關</span><span class="sxs-lookup"><span data-stu-id="f12c4-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="f12c4-223">關</span><span class="sxs-lookup"><span data-stu-id="f12c4-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f12c4-224">32770</span><span class="sxs-lookup"><span data-stu-id="f12c4-224">32770</span></span></p></td>
<td><p><span data-ttu-id="f12c4-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="f12c4-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="f12c4-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="f12c4-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

