---
title: Lync Server 2013： 設定會議、 應用程式及中繼伺服器的連接埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="54351-102">Lync Server 2013 中設定的連接埠範圍，會議、 應用程式及中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="54351-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54351-103">_**主題上次修改日期：** 2015年-04-30_</span><span class="sxs-lookup"><span data-stu-id="54351-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="54351-p101">為了實作服務品質 (QoS) ，您應該為在會議、應用程式和中繼伺服器上共用的音訊、視訊和應用程式共用，設定完全相同的連接埠範圍；此外，這些連接埠範圍不得以任何方式重疊。舉個簡單的例子，假設您針對會議伺服器上的視訊使用連接埠 10000 到 10999。這表示您也必須為應用程式和中繼伺服器上的視訊保留連接埠 10000 到 10999。如果沒有，服務品質 (QoS) 將無法如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="54351-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="54351-p102">同樣地，假設您為視訊保留連接埠 10000 到 10999，但接著為音訊保留連接埠 10500 到 11999。這樣會造成服務品質的問題，因為連接埠範圍重疊。使用服務品質 (QoS) 時，每一種模式都必須有一組唯一的連接埠：如果您對視訊使用連接埠 10000 到 10999，則必須使用不同的範圍 (例如，對音訊使用 11000 到 11999)。</span><span class="sxs-lookup"><span data-stu-id="54351-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="54351-111">根據預設，音訊和視訊的連接埠範圍中不會重疊 Microsoft Lync Server 2013;不過，連接埠範圍指派給應用程式共用與這兩個音訊和視訊的連接埠範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="54351-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="54351-112">（，接著，表示沒有任何這些範圍特有）。您可以執行從 Lync Server 2013 管理命令介面中的下列三個命令，會議、 應用程式及中繼伺服器驗證的現有的連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="54351-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="54351-p104">如同您在上述命令中所見，每一種連接埠類型 (音訊、視訊和應用程式共用) 都會被指派兩個不同的屬性值：連接埠起點和連接埠計數。連接埠起點指出用於該形式的第一個連接埠；例如，如果音訊連接埠起點等於 50000，表示用於音訊流量的第一個連接埠是連接埠 50000。如果音訊連接埠計數是 2 (這不是有效值，在這裡是作為說明之用) 表示只為音訊配置 2 個連接埠。如果第一個連接埠是連接埠 50000，且總共有兩個連接埠，表示第二個連接埠一定是連接埠 50001 (連接埠範圍必須是連續的)。因此，音訊的連接埠範圍將會是連接埠 50000 到 50001 (含)。</span><span class="sxs-lookup"><span data-stu-id="54351-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="54351-118">另請注意，應用程式伺服器和中繼伺服器只支援音訊的服務品質；您不需要在應用程式伺服器或中繼伺服器中變更視訊或應用程式共用連接埠。</span><span class="sxs-lookup"><span data-stu-id="54351-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="54351-119">如果您執行上述的三個命令，您會看到 Lync Server 2013 的預設連接埠值的設定如下：</span><span class="sxs-lookup"><span data-stu-id="54351-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54351-120">屬性	</span><span class="sxs-lookup"><span data-stu-id="54351-120">Property</span></span></th>
<th><span data-ttu-id="54351-121">會議伺服器</span><span class="sxs-lookup"><span data-stu-id="54351-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="54351-122">應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="54351-122">Application Server</span></span></th>
<th><span data-ttu-id="54351-123">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="54351-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54351-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="54351-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="54351-125">49152</span><span class="sxs-lookup"><span data-stu-id="54351-125">49152</span></span></p></td>
<td><p><span data-ttu-id="54351-126">49152</span><span class="sxs-lookup"><span data-stu-id="54351-126">49152</span></span></p></td>
<td><p><span data-ttu-id="54351-127">49152</span><span class="sxs-lookup"><span data-stu-id="54351-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54351-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="54351-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="54351-129">8348</span><span class="sxs-lookup"><span data-stu-id="54351-129">8348</span></span></p></td>
<td><p><span data-ttu-id="54351-130">8348</span><span class="sxs-lookup"><span data-stu-id="54351-130">8348</span></span></p></td>
<td><p><span data-ttu-id="54351-131">8348</span><span class="sxs-lookup"><span data-stu-id="54351-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54351-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="54351-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="54351-133">57501</span><span class="sxs-lookup"><span data-stu-id="54351-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54351-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="54351-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="54351-135">8034</span><span class="sxs-lookup"><span data-stu-id="54351-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54351-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="54351-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="54351-137">49152</span><span class="sxs-lookup"><span data-stu-id="54351-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54351-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="54351-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="54351-139">16383</span><span class="sxs-lookup"><span data-stu-id="54351-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="54351-140">如前所述，當 QoS 設定 Lync Server 連接埠，則您應該確保： 1) 音訊連接埠設定都是相同其他會議、 應用程式及中繼伺服器;和，2） 的連接埠範圍不會重疊。</span><span class="sxs-lookup"><span data-stu-id="54351-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="54351-141">如果您仔細查看上述表格中，您會看到的連接埠範圍皆相同，不同的三種伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="54351-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="54351-142">例如，起始音訊連接埠設為每個伺服器類型] 上的連接埠 49152 和音訊每部伺服器中已保留連接埠總數也是相同： 8348。</span><span class="sxs-lookup"><span data-stu-id="54351-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="54351-143">不過，連接埠範圍重疊： 音訊連接埠從 49152，開始，但是這樣執行動作的連接埠設定放在一旁應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="54351-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="54351-144">若要讓服務品質的最佳使用方式，應用程式共用應該會重新設定為使用唯一的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="54351-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="54351-145">例如，您可以設定應用程式共用連接埠 40803 處開始，並使用 8348 連接埠。</span><span class="sxs-lookup"><span data-stu-id="54351-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="54351-146">(為什麼 8348 連接埠嗎？</span><span class="sxs-lookup"><span data-stu-id="54351-146">(Why 8348 ports?</span></span> <span data-ttu-id="54351-147">如果您將這些值相加-40803 + 8348-表示的應用程式共用將使用連接埠 40803 透過連接埠 49150。</span><span class="sxs-lookup"><span data-stu-id="54351-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="54351-148">因為音訊連接埠開始時沒有 49152 之前，您將不再有任何重疊的連接埠範圍。）</span><span class="sxs-lookup"><span data-stu-id="54351-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="54351-p106">在為應用程式共用選取新的連接埠範圍之後，可以使用 Set-CsConferencingServer Cmdlet 進行變更。您不需要在應用程式伺服器或中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。如果您決定要重新指派用於音效流量的連接埠，只要在這些伺服器上變更連接埠值即可。</span><span class="sxs-lookup"><span data-stu-id="54351-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="54351-152">若要修改單一會議伺服器上共用的應用程式的連接埠值會執行 Lync Server 管理命令介面從如下的命令：</span><span class="sxs-lookup"><span data-stu-id="54351-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="54351-153">如果您要在所有的會議伺服器上進行這些變更，可以改為執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="54351-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="54351-154">在變更連接埠設定之後，您應該要先停止，然後再重新啟動每一項受到變更影響的服務。</span><span class="sxs-lookup"><span data-stu-id="54351-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="54351-p107">您的會議伺服器、應用程式伺服器和中繼伺服器並不是一定要共用完全相同的連接埠範圍；唯一必要的需求是您要在所有的伺服器上預留唯一的連接埠範圍。不過，如果您在所有伺服器上使用同一組連接埠，通常會讓管理工作更為輕鬆。</span><span class="sxs-lookup"><span data-stu-id="54351-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

