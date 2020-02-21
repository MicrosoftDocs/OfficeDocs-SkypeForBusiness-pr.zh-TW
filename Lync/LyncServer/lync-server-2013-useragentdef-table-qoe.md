---
title: 'Lync Server 2013: UserAgentDef 資料表 (QoE)'
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
ms.openlocfilehash: d2daba0f4e37a07065edf6a9c80955047a7d26b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragentdef-table-qoe-in-lync-server-2013"></a><span data-ttu-id="02398-102">Lync Server 2013 中的 UserAgentDef 資料表 (QoE)</span><span class="sxs-lookup"><span data-stu-id="02398-102">UserAgentDef table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02398-103">_**上次修改主題：** 2014年-03-25_</span><span class="sxs-lookup"><span data-stu-id="02398-103">_**Topic Last Modified:** 2014-03-25_</span></span>

<span data-ttu-id="02398-104">UserAgentDef 資料表將使用者代理程式識別碼對應至代理程式的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="02398-104">The UserAgentDef table maps user agent identifiers to the agent’s descriptive names.</span></span> <span data-ttu-id="02398-105">使用者代理程式是用來連線至 Microsoft Lync Server 2013 的軟體用戶端。</span><span class="sxs-lookup"><span data-stu-id="02398-105">User agents are software clients used to connect to Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02398-106">UAType</span><span class="sxs-lookup"><span data-stu-id="02398-106">UAType</span></span></th>
<th><span data-ttu-id="02398-107">UAName</span><span class="sxs-lookup"><span data-stu-id="02398-107">UAName</span></span></th>
<th><span data-ttu-id="02398-108">UACategory</span><span class="sxs-lookup"><span data-stu-id="02398-108">UACategory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02398-109">1</span><span class="sxs-lookup"><span data-stu-id="02398-109">1</span></span></p></td>
<td><p><span data-ttu-id="02398-110">MediationServer</span><span class="sxs-lookup"><span data-stu-id="02398-110">MediationServer</span></span></p></td>
<td><p><span data-ttu-id="02398-111">MediationServer</span><span class="sxs-lookup"><span data-stu-id="02398-111">MediationServer</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-112">2</span><span class="sxs-lookup"><span data-stu-id="02398-112">2</span></span></p></td>
<td><p><span data-ttu-id="02398-113">AV MCU</span><span class="sxs-lookup"><span data-stu-id="02398-113">AV-MCU</span></span></p></td>
<td><p><span data-ttu-id="02398-114">AV MCU</span><span class="sxs-lookup"><span data-stu-id="02398-114">AV-MCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-115">4</span><span class="sxs-lookup"><span data-stu-id="02398-115">4</span></span></p></td>
<td><p><span data-ttu-id="02398-116">OC</span><span class="sxs-lookup"><span data-stu-id="02398-116">OC</span></span></p></td>
<td><p><span data-ttu-id="02398-117">OC</span><span class="sxs-lookup"><span data-stu-id="02398-117">OC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-118">8 </span><span class="sxs-lookup"><span data-stu-id="02398-118">8</span></span></p></td>
<td><p><span data-ttu-id="02398-119">OCPhone</span><span class="sxs-lookup"><span data-stu-id="02398-119">OCPhone</span></span></p></td>
<td><p><span data-ttu-id="02398-120">OCPhone</span><span class="sxs-lookup"><span data-stu-id="02398-120">OCPhone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-121">16 </span><span class="sxs-lookup"><span data-stu-id="02398-121">16</span></span></p></td>
<td><p><span data-ttu-id="02398-122">LMC</span><span class="sxs-lookup"><span data-stu-id="02398-122">LMC</span></span></p></td>
<td><p><span data-ttu-id="02398-123">LMC</span><span class="sxs-lookup"><span data-stu-id="02398-123">LMC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-124">32</span><span class="sxs-lookup"><span data-stu-id="02398-124">32</span></span></p></td>
<td><p><span data-ttu-id="02398-125">DVT</span><span class="sxs-lookup"><span data-stu-id="02398-125">DVT</span></span></p></td>
<td><p><span data-ttu-id="02398-126">DVT</span><span class="sxs-lookup"><span data-stu-id="02398-126">DVT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-127">64</span><span class="sxs-lookup"><span data-stu-id="02398-127">64</span></span></p></td>
<td><p><span data-ttu-id="02398-128">公釐</span><span class="sxs-lookup"><span data-stu-id="02398-128">MM</span></span></p></td>
<td><p><span data-ttu-id="02398-129">公釐</span><span class="sxs-lookup"><span data-stu-id="02398-129">MM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-130">64</span><span class="sxs-lookup"><span data-stu-id="02398-130">64</span></span></p></td>
<td><p><span data-ttu-id="02398-131">MC</span><span class="sxs-lookup"><span data-stu-id="02398-131">MC</span></span></p></td>
<td><p><span data-ttu-id="02398-132">公釐</span><span class="sxs-lookup"><span data-stu-id="02398-132">MM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-133">128</span><span class="sxs-lookup"><span data-stu-id="02398-133">128</span></span></p></td>
<td><p><span data-ttu-id="02398-134">語音應答</span><span class="sxs-lookup"><span data-stu-id="02398-134">Attendant</span></span></p></td>
<td><p><span data-ttu-id="02398-135">語音應答</span><span class="sxs-lookup"><span data-stu-id="02398-135">Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-136">256</span><span class="sxs-lookup"><span data-stu-id="02398-136">256</span></span></p></td>
<td><p><span data-ttu-id="02398-137">Conferencing_Announcement_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="02398-137">Conferencing_Announcement_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="02398-138">CAS</span><span class="sxs-lookup"><span data-stu-id="02398-138">CAS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-139">512</span><span class="sxs-lookup"><span data-stu-id="02398-139">512</span></span></p></td>
<td><p><span data-ttu-id="02398-140">Conferencing_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="02398-140">Conferencing_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="02398-141">CAA</span><span class="sxs-lookup"><span data-stu-id="02398-141">CAA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-142">512</span><span class="sxs-lookup"><span data-stu-id="02398-142">512</span></span></p></td>
<td><p><span data-ttu-id="02398-143">Conference_Auto_Attendant_1.0</span><span class="sxs-lookup"><span data-stu-id="02398-143">Conference_Auto_Attendant_1.0</span></span></p></td>
<td><p><span data-ttu-id="02398-144">CAA</span><span class="sxs-lookup"><span data-stu-id="02398-144">CAA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-145">1024</span><span class="sxs-lookup"><span data-stu-id="02398-145">1024</span></span></p></td>
<td><p><span data-ttu-id="02398-146">Response_Group_Service</span><span class="sxs-lookup"><span data-stu-id="02398-146">Response_Group_Service</span></span></p></td>
<td><p><span data-ttu-id="02398-147">RGS</span><span class="sxs-lookup"><span data-stu-id="02398-147">RGS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-148">1032</span><span class="sxs-lookup"><span data-stu-id="02398-148">1032</span></span></p></td>
<td><p><span data-ttu-id="02398-149">Call_Park_Service_1.0</span><span class="sxs-lookup"><span data-stu-id="02398-149">Call_Park_Service_1.0</span></span></p></td>
<td><p><span data-ttu-id="02398-150">CPS</span><span class="sxs-lookup"><span data-stu-id="02398-150">CPS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-151">1040</span><span class="sxs-lookup"><span data-stu-id="02398-151">1040</span></span></p></td>
<td><p><span data-ttu-id="02398-152">Response_Group_Service Announcement_Service</span><span class="sxs-lookup"><span data-stu-id="02398-152">Response_Group_Service Announcement_Service</span></span></p></td>
<td><p><span data-ttu-id="02398-153">AS</span><span class="sxs-lookup"><span data-stu-id="02398-153">AS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-154">2048</span><span class="sxs-lookup"><span data-stu-id="02398-154">2048</span></span></p></td>
<td><p><span data-ttu-id="02398-155">Microsoft.Rtc.Applications.Ccs</span><span class="sxs-lookup"><span data-stu-id="02398-155">Microsoft.Rtc.Applications.Ccs</span></span></p></td>
<td><p><span data-ttu-id="02398-156">CCS</span><span class="sxs-lookup"><span data-stu-id="02398-156">CCS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-157">16386</span><span class="sxs-lookup"><span data-stu-id="02398-157">16386</span></span></p></td>
<td><p><span data-ttu-id="02398-158">CoMo</span><span class="sxs-lookup"><span data-stu-id="02398-158">CoMo</span></span></p></td>
<td><p><span data-ttu-id="02398-159">CoMo</span><span class="sxs-lookup"><span data-stu-id="02398-159">CoMo</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-160">16387</span><span class="sxs-lookup"><span data-stu-id="02398-160">16387</span></span></p></td>
<td><p><span data-ttu-id="02398-161">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="02398-161">CWA</span></span></p></td>
<td><p><span data-ttu-id="02398-162">NM-CWA-13-NO-VERSION</span><span class="sxs-lookup"><span data-stu-id="02398-162">CWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-163">16388</span><span class="sxs-lookup"><span data-stu-id="02398-163">16388</span></span></p></td>
<td><p><span data-ttu-id="02398-164">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="02398-164">InboundRouting</span></span></p></td>
<td><p><span data-ttu-id="02398-165">InboundRouting</span><span class="sxs-lookup"><span data-stu-id="02398-165">InboundRouting</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-166">16389</span><span class="sxs-lookup"><span data-stu-id="02398-166">16389</span></span></p></td>
<td><p><span data-ttu-id="02398-167">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="02398-167">ComoSvc</span></span></p></td>
<td><p><span data-ttu-id="02398-168">ComoSvc</span><span class="sxs-lookup"><span data-stu-id="02398-168">ComoSvc</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-169">16393</span><span class="sxs-lookup"><span data-stu-id="02398-169">16393</span></span></p></td>
<td><p><span data-ttu-id="02398-170">MSExchangeUM</span><span class="sxs-lookup"><span data-stu-id="02398-170">MSExchangeUM</span></span></p></td>
<td><p><span data-ttu-id="02398-171">ExUM</span><span class="sxs-lookup"><span data-stu-id="02398-171">ExUM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-172">16395</span><span class="sxs-lookup"><span data-stu-id="02398-172">16395</span></span></p></td>
<td><p><span data-ttu-id="02398-173">ArchivingAgent</span><span class="sxs-lookup"><span data-stu-id="02398-173">ArchivingAgent</span></span></p></td>
<td><p><span data-ttu-id="02398-174">ARCHAGENT</span><span class="sxs-lookup"><span data-stu-id="02398-174">ARCHAGENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-175">16396</span><span class="sxs-lookup"><span data-stu-id="02398-175">16396</span></span></p></td>
<td><p><span data-ttu-id="02398-176">ST</span><span class="sxs-lookup"><span data-stu-id="02398-176">ST</span></span></p></td>
<td><p><span data-ttu-id="02398-177">ST</span><span class="sxs-lookup"><span data-stu-id="02398-177">ST</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-178">16397</span><span class="sxs-lookup"><span data-stu-id="02398-178">16397</span></span></p></td>
<td><p><span data-ttu-id="02398-179">applicationsharing</span><span class="sxs-lookup"><span data-stu-id="02398-179">applicationsharing</span></span></p></td>
<td><p><span data-ttu-id="02398-180">ASMCU</span><span class="sxs-lookup"><span data-stu-id="02398-180">ASMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-181">16398</span><span class="sxs-lookup"><span data-stu-id="02398-181">16398</span></span></p></td>
<td><p><span data-ttu-id="02398-182">WPLync</span><span class="sxs-lookup"><span data-stu-id="02398-182">WPLync</span></span></p></td>
<td><p><span data-ttu-id="02398-183">WPLync</span><span class="sxs-lookup"><span data-stu-id="02398-183">WPLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-184">16399</span><span class="sxs-lookup"><span data-stu-id="02398-184">16399</span></span></p></td>
<td><p><span data-ttu-id="02398-185">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="02398-185">iPhoneLync</span></span></p></td>
<td><p><span data-ttu-id="02398-186">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="02398-186">iPhoneLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-187">16400</span><span class="sxs-lookup"><span data-stu-id="02398-187">16400</span></span></p></td>
<td><p><span data-ttu-id="02398-188">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="02398-188">AndroidLync</span></span></p></td>
<td><p><span data-ttu-id="02398-189">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="02398-189">AndroidLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-190">16401</span><span class="sxs-lookup"><span data-stu-id="02398-190">16401</span></span></p></td>
<td><p><span data-ttu-id="02398-191">iPadLync</span><span class="sxs-lookup"><span data-stu-id="02398-191">iPadLync</span></span></p></td>
<td><p><span data-ttu-id="02398-192">iPadLync</span><span class="sxs-lookup"><span data-stu-id="02398-192">iPadLync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-193">16402</span><span class="sxs-lookup"><span data-stu-id="02398-193">16402</span></span></p></td>
<td><p><span data-ttu-id="02398-194">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="02398-194">NokiaLync</span></span></p></td>
<td><p><span data-ttu-id="02398-195">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="02398-195">NokiaLync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-196">16403</span><span class="sxs-lookup"><span data-stu-id="02398-196">16403</span></span></p></td>
<td><p><span data-ttu-id="02398-197">LyncImm</span><span class="sxs-lookup"><span data-stu-id="02398-197">LyncImm</span></span></p></td>
<td><p><span data-ttu-id="02398-198">LyncImm</span><span class="sxs-lookup"><span data-stu-id="02398-198">LyncImm</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-199">16404</span><span class="sxs-lookup"><span data-stu-id="02398-199">16404</span></span></p></td>
<td><p><span data-ttu-id="02398-200">電腦</span><span class="sxs-lookup"><span data-stu-id="02398-200">PCS</span></span></p></td>
<td><p><span data-ttu-id="02398-201">電腦</span><span class="sxs-lookup"><span data-stu-id="02398-201">PCS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-202">16405</span><span class="sxs-lookup"><span data-stu-id="02398-202">16405</span></span></p></td>
<td><p><span data-ttu-id="02398-203">LWA</span><span class="sxs-lookup"><span data-stu-id="02398-203">LWA</span></span></p></td>
<td><p><span data-ttu-id="02398-204">LWA</span><span class="sxs-lookup"><span data-stu-id="02398-204">LWA</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-205">16406</span><span class="sxs-lookup"><span data-stu-id="02398-205">16406</span></span></p></td>
<td><p><span data-ttu-id="02398-206">OWA</span><span class="sxs-lookup"><span data-stu-id="02398-206">OWA</span></span></p></td>
<td><p><span data-ttu-id="02398-207">OWA</span><span class="sxs-lookup"><span data-stu-id="02398-207">OWA</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-208">16407</span><span class="sxs-lookup"><span data-stu-id="02398-208">16407</span></span></p></td>
<td><p><span data-ttu-id="02398-209">AOC</span><span class="sxs-lookup"><span data-stu-id="02398-209">AOC</span></span></p></td>
<td><p><span data-ttu-id="02398-210">AOC</span><span class="sxs-lookup"><span data-stu-id="02398-210">AOC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-211">16408</span><span class="sxs-lookup"><span data-stu-id="02398-211">16408</span></span></p></td>
<td><p><span data-ttu-id="02398-212">GCC</span><span class="sxs-lookup"><span data-stu-id="02398-212">GCC</span></span></p></td>
<td><p><span data-ttu-id="02398-213">GCC</span><span class="sxs-lookup"><span data-stu-id="02398-213">GCC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-214">16409</span><span class="sxs-lookup"><span data-stu-id="02398-214">16409</span></span></p></td>
<td><p><span data-ttu-id="02398-215">IMMCU</span><span class="sxs-lookup"><span data-stu-id="02398-215">IMMCU</span></span></p></td>
<td><p><span data-ttu-id="02398-216">IMMCU</span><span class="sxs-lookup"><span data-stu-id="02398-216">IMMCU</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-217">16410</span><span class="sxs-lookup"><span data-stu-id="02398-217">16410</span></span></p></td>
<td><p><span data-ttu-id="02398-218">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="02398-218">XmppTGW</span></span></p></td>
<td><p><span data-ttu-id="02398-219">XmppGateway</span><span class="sxs-lookup"><span data-stu-id="02398-219">XmppGateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02398-220">32769</span><span class="sxs-lookup"><span data-stu-id="02398-220">32769</span></span></p></td>
<td><p><span data-ttu-id="02398-221">閘道</span><span class="sxs-lookup"><span data-stu-id="02398-221">Gateway</span></span></p></td>
<td><p><span data-ttu-id="02398-222">閘道</span><span class="sxs-lookup"><span data-stu-id="02398-222">Gateway</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02398-223">32770</span><span class="sxs-lookup"><span data-stu-id="02398-223">32770</span></span></p></td>
<td><p><span data-ttu-id="02398-224">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="02398-224">GatewayMediationServerPair</span></span></p></td>
<td><p><span data-ttu-id="02398-225">GatewayMediationServerPair</span><span class="sxs-lookup"><span data-stu-id="02398-225">GatewayMediationServerPair</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

