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
ms.openlocfilehash: 0996abb7098ba636fc31d27388257f570a549ce2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="60234-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="60234-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60234-103">_**上次修改主題：** 2014年-03-25_</span><span class="sxs-lookup"><span data-stu-id="60234-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="60234-104">UserAgentDef 資料表將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="60234-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="60234-105">使用者代理程式是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="60234-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="60234-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="60234-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60234-107">UAType</span><span class="sxs-lookup"><span data-stu-id="60234-107">UAType</span></span></th>
<th><span data-ttu-id="60234-108">UAName</span><span class="sxs-lookup"><span data-stu-id="60234-108">UAName</span></span></th>
<th><span data-ttu-id="60234-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="60234-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60234-110">1 </span><span class="sxs-lookup"><span data-stu-id="60234-110">1</span></span></p></td>
<td><p><span data-ttu-id="60234-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="60234-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="60234-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="60234-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-113">2 </span><span class="sxs-lookup"><span data-stu-id="60234-113">2</span></span></p></td>
<td><p><span data-ttu-id="60234-114">AV MCU</span><span class="sxs-lookup"><span data-stu-id="60234-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="60234-115">AV MCU</span><span class="sxs-lookup"><span data-stu-id="60234-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-116">4 </span><span class="sxs-lookup"><span data-stu-id="60234-116">4</span></span></p></td>
<td><p><span data-ttu-id="60234-117">OC</span><span class="sxs-lookup"><span data-stu-id="60234-117">OC</span></span></p></td>
<td><p><span data-ttu-id="60234-118">OC</span><span class="sxs-lookup"><span data-stu-id="60234-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-119">8 </span><span class="sxs-lookup"><span data-stu-id="60234-119">8</span></span></p></td>
<td><p><span data-ttu-id="60234-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="60234-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="60234-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="60234-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-122">16 </span><span class="sxs-lookup"><span data-stu-id="60234-122">16</span></span></p></td>
<td><p><span data-ttu-id="60234-123">LMC</span><span class="sxs-lookup"><span data-stu-id="60234-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="60234-124">LMC</span><span class="sxs-lookup"><span data-stu-id="60234-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-125">32</span><span class="sxs-lookup"><span data-stu-id="60234-125">32</span></span></p></td>
<td><p><span data-ttu-id="60234-126">DVT</span><span class="sxs-lookup"><span data-stu-id="60234-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="60234-127">DVT</span><span class="sxs-lookup"><span data-stu-id="60234-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-128">64</span><span class="sxs-lookup"><span data-stu-id="60234-128">64</span></span></p></td>
<td><p><span data-ttu-id="60234-129">公釐</span><span class="sxs-lookup"><span data-stu-id="60234-129">MM</span></span></p></td>
<td><p><span data-ttu-id="60234-130">公釐</span><span class="sxs-lookup"><span data-stu-id="60234-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-131">64</span><span class="sxs-lookup"><span data-stu-id="60234-131">64</span></span></p></td>
<td><p><span data-ttu-id="60234-132">MC</span><span class="sxs-lookup"><span data-stu-id="60234-132">MC</span></span></p></td>
<td><p><span data-ttu-id="60234-133">公釐</span><span class="sxs-lookup"><span data-stu-id="60234-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-134">128</span><span class="sxs-lookup"><span data-stu-id="60234-134">128</span></span></p></td>
<td><p><span data-ttu-id="60234-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="60234-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="60234-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="60234-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-137">256</span><span class="sxs-lookup"><span data-stu-id="60234-137">256</span></span></p></td>
<td><p><span data-ttu-id="60234-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="60234-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="60234-139">CAS</span><span class="sxs-lookup"><span data-stu-id="60234-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-140">512</span><span class="sxs-lookup"><span data-stu-id="60234-140">512</span></span></p></td>
<td><p><span data-ttu-id="60234-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="60234-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="60234-142">CAA</span><span class="sxs-lookup"><span data-stu-id="60234-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-143">512</span><span class="sxs-lookup"><span data-stu-id="60234-143">512</span></span></p></td>
<td><p><span data-ttu-id="60234-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="60234-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="60234-145">CAA</span><span class="sxs-lookup"><span data-stu-id="60234-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-146">1024</span><span class="sxs-lookup"><span data-stu-id="60234-146">1024</span></span></p></td>
<td><p><span data-ttu-id="60234-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="60234-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="60234-148">RGS</span><span class="sxs-lookup"><span data-stu-id="60234-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-149">1032</span><span class="sxs-lookup"><span data-stu-id="60234-149">1032</span></span></p></td>
<td><p><span data-ttu-id="60234-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="60234-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="60234-151">CPS</span><span class="sxs-lookup"><span data-stu-id="60234-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-152">1040</span><span class="sxs-lookup"><span data-stu-id="60234-152">1040</span></span></p></td>
<td><p><span data-ttu-id="60234-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="60234-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="60234-154">AS</span><span class="sxs-lookup"><span data-stu-id="60234-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-155">2048</span><span class="sxs-lookup"><span data-stu-id="60234-155">2048</span></span></p></td>
<td><p><span data-ttu-id="60234-156">Microsoft.Rtc.Applications.Ccs</span><span class="sxs-lookup"><span data-stu-id="60234-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="60234-157">CCS</span><span class="sxs-lookup"><span data-stu-id="60234-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-158">16386</span><span class="sxs-lookup"><span data-stu-id="60234-158">16386</span></span></p></td>
<td><p><span data-ttu-id="60234-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="60234-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="60234-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="60234-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-161">16387</span><span class="sxs-lookup"><span data-stu-id="60234-161">16387</span></span></p></td>
<td><p><span data-ttu-id="60234-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="60234-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="60234-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="60234-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-164">16388</span><span class="sxs-lookup"><span data-stu-id="60234-164">16388</span></span></p></td>
<td><p><span data-ttu-id="60234-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="60234-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="60234-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="60234-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-167">16389</span><span class="sxs-lookup"><span data-stu-id="60234-167">16389</span></span></p></td>
<td><p><span data-ttu-id="60234-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="60234-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="60234-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="60234-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-170">16393</span><span class="sxs-lookup"><span data-stu-id="60234-170">16393</span></span></p></td>
<td><p><span data-ttu-id="60234-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="60234-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="60234-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="60234-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-173">16395</span><span class="sxs-lookup"><span data-stu-id="60234-173">16395</span></span></p></td>
<td><p><span data-ttu-id="60234-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="60234-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="60234-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="60234-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-176">16396</span><span class="sxs-lookup"><span data-stu-id="60234-176">16396</span></span></p></td>
<td><p><span data-ttu-id="60234-177">ST</span><span class="sxs-lookup"><span data-stu-id="60234-177">ST</span></span></p></td>
<td><p><span data-ttu-id="60234-178">ST</span><span class="sxs-lookup"><span data-stu-id="60234-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-179">16397</span><span class="sxs-lookup"><span data-stu-id="60234-179">16397</span></span></p></td>
<td><p><span data-ttu-id="60234-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="60234-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="60234-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="60234-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-182">16398</span><span class="sxs-lookup"><span data-stu-id="60234-182">16398</span></span></p></td>
<td><p><span data-ttu-id="60234-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="60234-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="60234-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="60234-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-185">16399</span><span class="sxs-lookup"><span data-stu-id="60234-185">16399</span></span></p></td>
<td><p><span data-ttu-id="60234-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="60234-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="60234-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="60234-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-188">16400</span><span class="sxs-lookup"><span data-stu-id="60234-188">16400</span></span></p></td>
<td><p><span data-ttu-id="60234-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="60234-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="60234-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="60234-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-191">16401</span><span class="sxs-lookup"><span data-stu-id="60234-191">16401</span></span></p></td>
<td><p><span data-ttu-id="60234-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="60234-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="60234-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="60234-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-194">16402</span><span class="sxs-lookup"><span data-stu-id="60234-194">16402</span></span></p></td>
<td><p><span data-ttu-id="60234-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="60234-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="60234-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="60234-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-197">16403</span><span class="sxs-lookup"><span data-stu-id="60234-197">16403</span></span></p></td>
<td><p><span data-ttu-id="60234-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="60234-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="60234-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="60234-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-200">16404</span><span class="sxs-lookup"><span data-stu-id="60234-200">16404</span></span></p></td>
<td><p><span data-ttu-id="60234-201">電腦</span><span class="sxs-lookup"><span data-stu-id="60234-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="60234-202">電腦</span><span class="sxs-lookup"><span data-stu-id="60234-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-203">16405</span><span class="sxs-lookup"><span data-stu-id="60234-203">16405</span></span></p></td>
<td><p><span data-ttu-id="60234-204">LWA</span><span class="sxs-lookup"><span data-stu-id="60234-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="60234-205">LWA</span><span class="sxs-lookup"><span data-stu-id="60234-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-206">16406</span><span class="sxs-lookup"><span data-stu-id="60234-206">16406</span></span></p></td>
<td><p><span data-ttu-id="60234-207">OWA</span><span class="sxs-lookup"><span data-stu-id="60234-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="60234-208">OWA</span><span class="sxs-lookup"><span data-stu-id="60234-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-209">16407</span><span class="sxs-lookup"><span data-stu-id="60234-209">16407</span></span></p></td>
<td><p><span data-ttu-id="60234-210">AOC</span><span class="sxs-lookup"><span data-stu-id="60234-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="60234-211">AOC</span><span class="sxs-lookup"><span data-stu-id="60234-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-212">16408</span><span class="sxs-lookup"><span data-stu-id="60234-212">16408</span></span></p></td>
<td><p><span data-ttu-id="60234-213">GCC</span><span class="sxs-lookup"><span data-stu-id="60234-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="60234-214">GCC</span><span class="sxs-lookup"><span data-stu-id="60234-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-215">16409</span><span class="sxs-lookup"><span data-stu-id="60234-215">16409</span></span></p></td>
<td><p><span data-ttu-id="60234-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="60234-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="60234-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="60234-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-218">16410</span><span class="sxs-lookup"><span data-stu-id="60234-218">16410</span></span></p></td>
<td><p><span data-ttu-id="60234-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="60234-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="60234-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="60234-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60234-221">32769</span><span class="sxs-lookup"><span data-stu-id="60234-221">32769</span></span></p></td>
<td><p><span data-ttu-id="60234-222">閘道</span><span class="sxs-lookup"><span data-stu-id="60234-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="60234-223">閘道</span><span class="sxs-lookup"><span data-stu-id="60234-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60234-224">32770</span><span class="sxs-lookup"><span data-stu-id="60234-224">32770</span></span></p></td>
<td><p><span data-ttu-id="60234-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="60234-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="60234-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="60234-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

