---
title: 'Lync Server 2013: UserAgentDef 表'
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
ms.openlocfilehash: b7f63c9e5194c2b75ea6f637acec7201c86178e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="1e77f-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="1e77f-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e77f-103">_**上次修改主題：** 2014年-03-25_</span><span class="sxs-lookup"><span data-stu-id="1e77f-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="1e77f-104">UserAgentDef 資料表將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="1e77f-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="1e77f-105">使用者代理程式是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="1e77f-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1e77f-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="1e77f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e77f-107">UAType</span><span class="sxs-lookup"><span data-stu-id="1e77f-107">UAType</span></span></th>
<th><span data-ttu-id="1e77f-108">UAName</span><span class="sxs-lookup"><span data-stu-id="1e77f-108">UAName</span></span></th>
<th><span data-ttu-id="1e77f-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="1e77f-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-110">1</span><span class="sxs-lookup"><span data-stu-id="1e77f-110">1</span></span></p></td>
<td><p><span data-ttu-id="1e77f-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1e77f-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="1e77f-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="1e77f-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-113">2</span><span class="sxs-lookup"><span data-stu-id="1e77f-113">2</span></span></p></td>
<td><p><span data-ttu-id="1e77f-114">AV MCU</span><span class="sxs-lookup"><span data-stu-id="1e77f-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="1e77f-115">AV MCU</span><span class="sxs-lookup"><span data-stu-id="1e77f-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-116">4</span><span class="sxs-lookup"><span data-stu-id="1e77f-116">4</span></span></p></td>
<td><p><span data-ttu-id="1e77f-117">OC</span><span class="sxs-lookup"><span data-stu-id="1e77f-117">OC</span></span></p></td>
<td><p><span data-ttu-id="1e77f-118">OC</span><span class="sxs-lookup"><span data-stu-id="1e77f-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-119">8 </span><span class="sxs-lookup"><span data-stu-id="1e77f-119">8</span></span></p></td>
<td><p><span data-ttu-id="1e77f-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="1e77f-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="1e77f-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="1e77f-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-122">16 </span><span class="sxs-lookup"><span data-stu-id="1e77f-122">16</span></span></p></td>
<td><p><span data-ttu-id="1e77f-123">LMC</span><span class="sxs-lookup"><span data-stu-id="1e77f-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="1e77f-124">LMC</span><span class="sxs-lookup"><span data-stu-id="1e77f-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-125">32</span><span class="sxs-lookup"><span data-stu-id="1e77f-125">32</span></span></p></td>
<td><p><span data-ttu-id="1e77f-126">DVT</span><span class="sxs-lookup"><span data-stu-id="1e77f-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="1e77f-127">DVT</span><span class="sxs-lookup"><span data-stu-id="1e77f-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-128">64</span><span class="sxs-lookup"><span data-stu-id="1e77f-128">64</span></span></p></td>
<td><p><span data-ttu-id="1e77f-129">公釐</span><span class="sxs-lookup"><span data-stu-id="1e77f-129">MM</span></span></p></td>
<td><p><span data-ttu-id="1e77f-130">公釐</span><span class="sxs-lookup"><span data-stu-id="1e77f-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-131">64</span><span class="sxs-lookup"><span data-stu-id="1e77f-131">64</span></span></p></td>
<td><p><span data-ttu-id="1e77f-132">MC</span><span class="sxs-lookup"><span data-stu-id="1e77f-132">MC</span></span></p></td>
<td><p><span data-ttu-id="1e77f-133">公釐</span><span class="sxs-lookup"><span data-stu-id="1e77f-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-134">128</span><span class="sxs-lookup"><span data-stu-id="1e77f-134">128</span></span></p></td>
<td><p><span data-ttu-id="1e77f-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="1e77f-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="1e77f-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="1e77f-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-137">256</span><span class="sxs-lookup"><span data-stu-id="1e77f-137">256</span></span></p></td>
<td><p><span data-ttu-id="1e77f-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="1e77f-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="1e77f-139">CAS</span><span class="sxs-lookup"><span data-stu-id="1e77f-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-140">512</span><span class="sxs-lookup"><span data-stu-id="1e77f-140">512</span></span></p></td>
<td><p><span data-ttu-id="1e77f-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="1e77f-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="1e77f-142">CAA</span><span class="sxs-lookup"><span data-stu-id="1e77f-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-143">512</span><span class="sxs-lookup"><span data-stu-id="1e77f-143">512</span></span></p></td>
<td><p><span data-ttu-id="1e77f-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="1e77f-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="1e77f-145">CAA</span><span class="sxs-lookup"><span data-stu-id="1e77f-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-146">1024</span><span class="sxs-lookup"><span data-stu-id="1e77f-146">1024</span></span></p></td>
<td><p><span data-ttu-id="1e77f-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="1e77f-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="1e77f-148">RGS</span><span class="sxs-lookup"><span data-stu-id="1e77f-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-149">1032</span><span class="sxs-lookup"><span data-stu-id="1e77f-149">1032</span></span></p></td>
<td><p><span data-ttu-id="1e77f-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="1e77f-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="1e77f-151">CPS</span><span class="sxs-lookup"><span data-stu-id="1e77f-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-152">1040</span><span class="sxs-lookup"><span data-stu-id="1e77f-152">1040</span></span></p></td>
<td><p><span data-ttu-id="1e77f-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="1e77f-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="1e77f-154">AS</span><span class="sxs-lookup"><span data-stu-id="1e77f-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-155">2048</span><span class="sxs-lookup"><span data-stu-id="1e77f-155">2048</span></span></p></td>
<td><p><span data-ttu-id="1e77f-156">Microsoft.Rtc.Applications.Ccs</span><span class="sxs-lookup"><span data-stu-id="1e77f-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="1e77f-157">CCS</span><span class="sxs-lookup"><span data-stu-id="1e77f-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-158">16386</span><span class="sxs-lookup"><span data-stu-id="1e77f-158">16386</span></span></p></td>
<td><p><span data-ttu-id="1e77f-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="1e77f-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="1e77f-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="1e77f-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-161">16387</span><span class="sxs-lookup"><span data-stu-id="1e77f-161">16387</span></span></p></td>
<td><p><span data-ttu-id="1e77f-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="1e77f-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="1e77f-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="1e77f-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-164">16388</span><span class="sxs-lookup"><span data-stu-id="1e77f-164">16388</span></span></p></td>
<td><p><span data-ttu-id="1e77f-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="1e77f-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="1e77f-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="1e77f-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-167">16389</span><span class="sxs-lookup"><span data-stu-id="1e77f-167">16389</span></span></p></td>
<td><p><span data-ttu-id="1e77f-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="1e77f-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="1e77f-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="1e77f-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-170">16393</span><span class="sxs-lookup"><span data-stu-id="1e77f-170">16393</span></span></p></td>
<td><p><span data-ttu-id="1e77f-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="1e77f-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="1e77f-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="1e77f-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-173">16395</span><span class="sxs-lookup"><span data-stu-id="1e77f-173">16395</span></span></p></td>
<td><p><span data-ttu-id="1e77f-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="1e77f-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="1e77f-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="1e77f-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-176">16396</span><span class="sxs-lookup"><span data-stu-id="1e77f-176">16396</span></span></p></td>
<td><p><span data-ttu-id="1e77f-177">ST</span><span class="sxs-lookup"><span data-stu-id="1e77f-177">ST</span></span></p></td>
<td><p><span data-ttu-id="1e77f-178">ST</span><span class="sxs-lookup"><span data-stu-id="1e77f-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-179">16397</span><span class="sxs-lookup"><span data-stu-id="1e77f-179">16397</span></span></p></td>
<td><p><span data-ttu-id="1e77f-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="1e77f-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="1e77f-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="1e77f-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-182">16398</span><span class="sxs-lookup"><span data-stu-id="1e77f-182">16398</span></span></p></td>
<td><p><span data-ttu-id="1e77f-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="1e77f-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-185">16399</span><span class="sxs-lookup"><span data-stu-id="1e77f-185">16399</span></span></p></td>
<td><p><span data-ttu-id="1e77f-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="1e77f-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-188">16400</span><span class="sxs-lookup"><span data-stu-id="1e77f-188">16400</span></span></p></td>
<td><p><span data-ttu-id="1e77f-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="1e77f-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-191">16401</span><span class="sxs-lookup"><span data-stu-id="1e77f-191">16401</span></span></p></td>
<td><p><span data-ttu-id="1e77f-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="1e77f-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-194">16402</span><span class="sxs-lookup"><span data-stu-id="1e77f-194">16402</span></span></p></td>
<td><p><span data-ttu-id="1e77f-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="1e77f-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="1e77f-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-197">16403</span><span class="sxs-lookup"><span data-stu-id="1e77f-197">16403</span></span></p></td>
<td><p><span data-ttu-id="1e77f-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="1e77f-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="1e77f-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="1e77f-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-200">16404</span><span class="sxs-lookup"><span data-stu-id="1e77f-200">16404</span></span></p></td>
<td><p><span data-ttu-id="1e77f-201">電腦</span><span class="sxs-lookup"><span data-stu-id="1e77f-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="1e77f-202">電腦</span><span class="sxs-lookup"><span data-stu-id="1e77f-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-203">16405</span><span class="sxs-lookup"><span data-stu-id="1e77f-203">16405</span></span></p></td>
<td><p><span data-ttu-id="1e77f-204">LWA</span><span class="sxs-lookup"><span data-stu-id="1e77f-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="1e77f-205">LWA</span><span class="sxs-lookup"><span data-stu-id="1e77f-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-206">16406</span><span class="sxs-lookup"><span data-stu-id="1e77f-206">16406</span></span></p></td>
<td><p><span data-ttu-id="1e77f-207">OWA</span><span class="sxs-lookup"><span data-stu-id="1e77f-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="1e77f-208">OWA</span><span class="sxs-lookup"><span data-stu-id="1e77f-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-209">16407</span><span class="sxs-lookup"><span data-stu-id="1e77f-209">16407</span></span></p></td>
<td><p><span data-ttu-id="1e77f-210">AOC</span><span class="sxs-lookup"><span data-stu-id="1e77f-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="1e77f-211">AOC</span><span class="sxs-lookup"><span data-stu-id="1e77f-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-212">16408</span><span class="sxs-lookup"><span data-stu-id="1e77f-212">16408</span></span></p></td>
<td><p><span data-ttu-id="1e77f-213">GCC</span><span class="sxs-lookup"><span data-stu-id="1e77f-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="1e77f-214">GCC</span><span class="sxs-lookup"><span data-stu-id="1e77f-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-215">16409</span><span class="sxs-lookup"><span data-stu-id="1e77f-215">16409</span></span></p></td>
<td><p><span data-ttu-id="1e77f-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="1e77f-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="1e77f-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="1e77f-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-218">16410</span><span class="sxs-lookup"><span data-stu-id="1e77f-218">16410</span></span></p></td>
<td><p><span data-ttu-id="1e77f-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="1e77f-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="1e77f-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="1e77f-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e77f-221">32769</span><span class="sxs-lookup"><span data-stu-id="1e77f-221">32769</span></span></p></td>
<td><p><span data-ttu-id="1e77f-222">閘道</span><span class="sxs-lookup"><span data-stu-id="1e77f-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="1e77f-223">閘道</span><span class="sxs-lookup"><span data-stu-id="1e77f-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e77f-224">32770</span><span class="sxs-lookup"><span data-stu-id="1e77f-224">32770</span></span></p></td>
<td><p><span data-ttu-id="1e77f-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="1e77f-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="1e77f-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="1e77f-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

