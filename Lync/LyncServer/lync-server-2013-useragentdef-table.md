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
ms.openlocfilehash: 621020816ae7882d25f65ab2a40578ddebcfe837
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-in-lync-server-2013"></a><span data-ttu-id="61069-102">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="61069-102">UserAgentDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61069-103">_**上次修改主題：** 2014年-03-25_</span><span class="sxs-lookup"><span data-stu-id="61069-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="61069-104">UserAgentDef 資料表將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="61069-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="61069-105">使用者代理程式是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="61069-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="61069-106">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="61069-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61069-107">UAType</span><span class="sxs-lookup"><span data-stu-id="61069-107">UAType</span></span></th>
<th><span data-ttu-id="61069-108">UAName</span><span class="sxs-lookup"><span data-stu-id="61069-108">UAName</span></span></th>
<th><span data-ttu-id="61069-109">UACategory</span><span class="sxs-lookup"><span data-stu-id="61069-109">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61069-110">1</span><span class="sxs-lookup"><span data-stu-id="61069-110">1</span></span></p></td>
<td><p><span data-ttu-id="61069-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="61069-111">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="61069-112">MediationServer</span><span class="sxs-lookup"><span data-stu-id="61069-112">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-113">2</span><span class="sxs-lookup"><span data-stu-id="61069-113">2</span></span></p></td>
<td><p><span data-ttu-id="61069-114">AV MCU</span><span class="sxs-lookup"><span data-stu-id="61069-114">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="61069-115">AV MCU</span><span class="sxs-lookup"><span data-stu-id="61069-115">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-116">4</span><span class="sxs-lookup"><span data-stu-id="61069-116">4</span></span></p></td>
<td><p><span data-ttu-id="61069-117">OC</span><span class="sxs-lookup"><span data-stu-id="61069-117">OC</span></span></p></td>
<td><p><span data-ttu-id="61069-118">OC</span><span class="sxs-lookup"><span data-stu-id="61069-118">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-119">8 </span><span class="sxs-lookup"><span data-stu-id="61069-119">8</span></span></p></td>
<td><p><span data-ttu-id="61069-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="61069-120">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="61069-121">OCPhone</span><span class="sxs-lookup"><span data-stu-id="61069-121">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-122">16 </span><span class="sxs-lookup"><span data-stu-id="61069-122">16</span></span></p></td>
<td><p><span data-ttu-id="61069-123">LMC</span><span class="sxs-lookup"><span data-stu-id="61069-123">LMC</span></span></p></td>
<td><p><span data-ttu-id="61069-124">LMC</span><span class="sxs-lookup"><span data-stu-id="61069-124">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-125">32</span><span class="sxs-lookup"><span data-stu-id="61069-125">32</span></span></p></td>
<td><p><span data-ttu-id="61069-126">DVT</span><span class="sxs-lookup"><span data-stu-id="61069-126">DVT</span></span></p></td>
<td><p><span data-ttu-id="61069-127">DVT</span><span class="sxs-lookup"><span data-stu-id="61069-127">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-128">64</span><span class="sxs-lookup"><span data-stu-id="61069-128">64</span></span></p></td>
<td><p><span data-ttu-id="61069-129">公釐</span><span class="sxs-lookup"><span data-stu-id="61069-129">MM</span></span></p></td>
<td><p><span data-ttu-id="61069-130">公釐</span><span class="sxs-lookup"><span data-stu-id="61069-130">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-131">64</span><span class="sxs-lookup"><span data-stu-id="61069-131">64</span></span></p></td>
<td><p><span data-ttu-id="61069-132">MC</span><span class="sxs-lookup"><span data-stu-id="61069-132">MC</span></span></p></td>
<td><p><span data-ttu-id="61069-133">公釐</span><span class="sxs-lookup"><span data-stu-id="61069-133">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-134">128</span><span class="sxs-lookup"><span data-stu-id="61069-134">128</span></span></p></td>
<td><p><span data-ttu-id="61069-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="61069-135">Attendant</span></span></p></td>
<td><p><span data-ttu-id="61069-136">語音應答</span><span class="sxs-lookup"><span data-stu-id="61069-136">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-137">256</span><span class="sxs-lookup"><span data-stu-id="61069-137">256</span></span></p></td>
<td><p><span data-ttu-id="61069-138">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="61069-138">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="61069-139">CAS</span><span class="sxs-lookup"><span data-stu-id="61069-139">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-140">512</span><span class="sxs-lookup"><span data-stu-id="61069-140">512</span></span></p></td>
<td><p><span data-ttu-id="61069-141">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="61069-141">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="61069-142">CAA</span><span class="sxs-lookup"><span data-stu-id="61069-142">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-143">512</span><span class="sxs-lookup"><span data-stu-id="61069-143">512</span></span></p></td>
<td><p><span data-ttu-id="61069-144">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="61069-144">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="61069-145">CAA</span><span class="sxs-lookup"><span data-stu-id="61069-145">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-146">1024</span><span class="sxs-lookup"><span data-stu-id="61069-146">1024</span></span></p></td>
<td><p><span data-ttu-id="61069-147">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="61069-147">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="61069-148">RGS</span><span class="sxs-lookup"><span data-stu-id="61069-148">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-149">1032</span><span class="sxs-lookup"><span data-stu-id="61069-149">1032</span></span></p></td>
<td><p><span data-ttu-id="61069-150">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="61069-150">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="61069-151">CPS</span><span class="sxs-lookup"><span data-stu-id="61069-151">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-152">1040</span><span class="sxs-lookup"><span data-stu-id="61069-152">1040</span></span></p></td>
<td><p><span data-ttu-id="61069-153">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="61069-153">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="61069-154">AS</span><span class="sxs-lookup"><span data-stu-id="61069-154">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-155">2048</span><span class="sxs-lookup"><span data-stu-id="61069-155">2048</span></span></p></td>
<td><p><span data-ttu-id="61069-156">Microsoft.Rtc.Applications.Ccs</span><span class="sxs-lookup"><span data-stu-id="61069-156">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="61069-157">CCS</span><span class="sxs-lookup"><span data-stu-id="61069-157">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-158">16386</span><span class="sxs-lookup"><span data-stu-id="61069-158">16386</span></span></p></td>
<td><p><span data-ttu-id="61069-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="61069-159">CoMo</span></span></p></td>
<td><p><span data-ttu-id="61069-160">CoMo</span><span class="sxs-lookup"><span data-stu-id="61069-160">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-161">16387</span><span class="sxs-lookup"><span data-stu-id="61069-161">16387</span></span></p></td>
<td><p><span data-ttu-id="61069-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="61069-162">CWA</span></span></p></td>
<td><p><span data-ttu-id="61069-163">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="61069-163">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-164">16388</span><span class="sxs-lookup"><span data-stu-id="61069-164">16388</span></span></p></td>
<td><p><span data-ttu-id="61069-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="61069-165">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="61069-166">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="61069-166">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-167">16389</span><span class="sxs-lookup"><span data-stu-id="61069-167">16389</span></span></p></td>
<td><p><span data-ttu-id="61069-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="61069-168">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="61069-169">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="61069-169">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-170">16393</span><span class="sxs-lookup"><span data-stu-id="61069-170">16393</span></span></p></td>
<td><p><span data-ttu-id="61069-171">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="61069-171">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="61069-172">ExUM</span><span class="sxs-lookup"><span data-stu-id="61069-172">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-173">16395</span><span class="sxs-lookup"><span data-stu-id="61069-173">16395</span></span></p></td>
<td><p><span data-ttu-id="61069-174">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="61069-174">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="61069-175">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="61069-175">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-176">16396</span><span class="sxs-lookup"><span data-stu-id="61069-176">16396</span></span></p></td>
<td><p><span data-ttu-id="61069-177">ST</span><span class="sxs-lookup"><span data-stu-id="61069-177">ST</span></span></p></td>
<td><p><span data-ttu-id="61069-178">ST</span><span class="sxs-lookup"><span data-stu-id="61069-178">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-179">16397</span><span class="sxs-lookup"><span data-stu-id="61069-179">16397</span></span></p></td>
<td><p><span data-ttu-id="61069-180">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="61069-180">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="61069-181">ASMCU</span><span class="sxs-lookup"><span data-stu-id="61069-181">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-182">16398</span><span class="sxs-lookup"><span data-stu-id="61069-182">16398</span></span></p></td>
<td><p><span data-ttu-id="61069-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="61069-183">WPLync</span></span></p></td>
<td><p><span data-ttu-id="61069-184">WPLync</span><span class="sxs-lookup"><span data-stu-id="61069-184">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-185">16399</span><span class="sxs-lookup"><span data-stu-id="61069-185">16399</span></span></p></td>
<td><p><span data-ttu-id="61069-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="61069-186">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="61069-187">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="61069-187">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-188">16400</span><span class="sxs-lookup"><span data-stu-id="61069-188">16400</span></span></p></td>
<td><p><span data-ttu-id="61069-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="61069-189">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="61069-190">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="61069-190">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-191">16401</span><span class="sxs-lookup"><span data-stu-id="61069-191">16401</span></span></p></td>
<td><p><span data-ttu-id="61069-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="61069-192">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="61069-193">iPadLync</span><span class="sxs-lookup"><span data-stu-id="61069-193">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-194">16402</span><span class="sxs-lookup"><span data-stu-id="61069-194">16402</span></span></p></td>
<td><p><span data-ttu-id="61069-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="61069-195">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="61069-196">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="61069-196">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-197">16403</span><span class="sxs-lookup"><span data-stu-id="61069-197">16403</span></span></p></td>
<td><p><span data-ttu-id="61069-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="61069-198">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="61069-199">LyncImm</span><span class="sxs-lookup"><span data-stu-id="61069-199">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-200">16404</span><span class="sxs-lookup"><span data-stu-id="61069-200">16404</span></span></p></td>
<td><p><span data-ttu-id="61069-201">電腦</span><span class="sxs-lookup"><span data-stu-id="61069-201">PCS</span></span></p></td>
<td><p><span data-ttu-id="61069-202">電腦</span><span class="sxs-lookup"><span data-stu-id="61069-202">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-203">16405</span><span class="sxs-lookup"><span data-stu-id="61069-203">16405</span></span></p></td>
<td><p><span data-ttu-id="61069-204">LWA</span><span class="sxs-lookup"><span data-stu-id="61069-204">LWA</span></span></p></td>
<td><p><span data-ttu-id="61069-205">LWA</span><span class="sxs-lookup"><span data-stu-id="61069-205">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-206">16406</span><span class="sxs-lookup"><span data-stu-id="61069-206">16406</span></span></p></td>
<td><p><span data-ttu-id="61069-207">OWA</span><span class="sxs-lookup"><span data-stu-id="61069-207">OWA</span></span></p></td>
<td><p><span data-ttu-id="61069-208">OWA</span><span class="sxs-lookup"><span data-stu-id="61069-208">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-209">16407</span><span class="sxs-lookup"><span data-stu-id="61069-209">16407</span></span></p></td>
<td><p><span data-ttu-id="61069-210">AOC</span><span class="sxs-lookup"><span data-stu-id="61069-210">AOC</span></span></p></td>
<td><p><span data-ttu-id="61069-211">AOC</span><span class="sxs-lookup"><span data-stu-id="61069-211">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-212">16408</span><span class="sxs-lookup"><span data-stu-id="61069-212">16408</span></span></p></td>
<td><p><span data-ttu-id="61069-213">GCC</span><span class="sxs-lookup"><span data-stu-id="61069-213">GCC</span></span></p></td>
<td><p><span data-ttu-id="61069-214">GCC</span><span class="sxs-lookup"><span data-stu-id="61069-214">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-215">16409</span><span class="sxs-lookup"><span data-stu-id="61069-215">16409</span></span></p></td>
<td><p><span data-ttu-id="61069-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="61069-216">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="61069-217">IMMCU</span><span class="sxs-lookup"><span data-stu-id="61069-217">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-218">16410</span><span class="sxs-lookup"><span data-stu-id="61069-218">16410</span></span></p></td>
<td><p><span data-ttu-id="61069-219">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="61069-219">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="61069-220">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="61069-220">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61069-221">32769</span><span class="sxs-lookup"><span data-stu-id="61069-221">32769</span></span></p></td>
<td><p><span data-ttu-id="61069-222">閘道</span><span class="sxs-lookup"><span data-stu-id="61069-222">Gateway</span></span></p></td>
<td><p><span data-ttu-id="61069-223">閘道</span><span class="sxs-lookup"><span data-stu-id="61069-223">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61069-224">32770</span><span class="sxs-lookup"><span data-stu-id="61069-224">32770</span></span></p></td>
<td><p><span data-ttu-id="61069-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="61069-225">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="61069-226">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="61069-226">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

