---
title: Lync Server 2013：針對您的會議、應用程式和中繼伺服器配置埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="dff13-102">在 Lync Server 2013 中針對您的會議、應用程式和中繼伺服器設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="dff13-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff13-103">_**主題上次修改日期：** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="dff13-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="dff13-104">為了實現服務品質，您應該在會議、應用程式和中繼伺服器上設定相同的埠範圍，以進行音訊、影片和應用程式共用;此外，這些埠範圍不一定會以任何方式重迭。</span><span class="sxs-lookup"><span data-stu-id="dff13-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="dff13-105">若要使用簡單的範例，假設您在會議服務器上使用埠10000到10999進行影片。</span><span class="sxs-lookup"><span data-stu-id="dff13-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="dff13-106">這表示您也必須在您的應用程式和轉送伺服器上為影片保留埠10000到10999。</span><span class="sxs-lookup"><span data-stu-id="dff13-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="dff13-107">否則，QoS 將無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="dff13-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="dff13-108">同樣地，假設您將埠10000到10999，以進行影片，但接著將埠10500到11999以進行音訊。</span><span class="sxs-lookup"><span data-stu-id="dff13-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="dff13-109">這可能會造成服務品質的問題，因為埠範圍會重迭。</span><span class="sxs-lookup"><span data-stu-id="dff13-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="dff13-110">有了 QoS，每個模態都必須有一組獨特的埠：如果您使用埠10000到10999進行影片，則必須使用不同的範圍（例如，從11000到11999的音訊）。</span><span class="sxs-lookup"><span data-stu-id="dff13-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="dff13-111">根據預設，音訊及視訊連接埠範圍不會在 Microsoft Lync Server 2013 中重迭;不過，指派給應用程式共用的埠範圍會與音訊與視訊連接埠範圍重迭。</span><span class="sxs-lookup"><span data-stu-id="dff13-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="dff13-112">（進而表示這些範圍都不是唯一的）。您可以在 Lync Server 2013 管理命令介面中執行下列三個命令，以驗證您的會議、應用程式和轉送作業伺服器的現有埠範圍：</span><span class="sxs-lookup"><span data-stu-id="dff13-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="dff13-113">您可以在前面的命令中看到，每個埠類型（音訊、影片和應用程式共用）都指派了兩個個別的屬性值：埠開始和埠數。</span><span class="sxs-lookup"><span data-stu-id="dff13-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="dff13-114">埠開始指示該模態使用的第一個埠;例如，如果音訊埠開始等於50000，表示音訊流量使用的第一個埠是埠50000。</span><span class="sxs-lookup"><span data-stu-id="dff13-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="dff13-115">如果音訊埠數是2（這是不正確值，但在這裡是用來做為說明），則表示只會為音訊分配兩個埠。</span><span class="sxs-lookup"><span data-stu-id="dff13-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="dff13-116">如果第一個埠是埠50000，而且總共有兩個埠，則表示第二個埠必須是埠50001（埠範圍必須是連續的）。</span><span class="sxs-lookup"><span data-stu-id="dff13-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="dff13-117">因此，音訊的埠範圍是埠50000到50001（含）。</span><span class="sxs-lookup"><span data-stu-id="dff13-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="dff13-118">請注意，應用程式伺服器和中繼伺服器只支援音訊的 QoS;您不需要變更應用程式伺服器或轉送伺服器中的影片或應用程式共用埠。</span><span class="sxs-lookup"><span data-stu-id="dff13-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="dff13-119">如果您執行前面三個命令，您會看到 Lync Server 2013 的預設埠值已設定為如下所示：</span><span class="sxs-lookup"><span data-stu-id="dff13-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dff13-120">Property</span><span class="sxs-lookup"><span data-stu-id="dff13-120">Property</span></span></th>
<th><span data-ttu-id="dff13-121">會議服務器</span><span class="sxs-lookup"><span data-stu-id="dff13-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="dff13-122">應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="dff13-122">Application Server</span></span></th>
<th><span data-ttu-id="dff13-123">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="dff13-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dff13-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="dff13-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="dff13-125">49152</span><span class="sxs-lookup"><span data-stu-id="dff13-125">49152</span></span></p></td>
<td><p><span data-ttu-id="dff13-126">49152</span><span class="sxs-lookup"><span data-stu-id="dff13-126">49152</span></span></p></td>
<td><p><span data-ttu-id="dff13-127">49152</span><span class="sxs-lookup"><span data-stu-id="dff13-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dff13-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="dff13-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="dff13-129">8348</span><span class="sxs-lookup"><span data-stu-id="dff13-129">8348</span></span></p></td>
<td><p><span data-ttu-id="dff13-130">8348</span><span class="sxs-lookup"><span data-stu-id="dff13-130">8348</span></span></p></td>
<td><p><span data-ttu-id="dff13-131">8348</span><span class="sxs-lookup"><span data-stu-id="dff13-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dff13-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="dff13-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="dff13-133">57501</span><span class="sxs-lookup"><span data-stu-id="dff13-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dff13-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="dff13-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="dff13-135">8034</span><span class="sxs-lookup"><span data-stu-id="dff13-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dff13-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="dff13-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="dff13-137">49152</span><span class="sxs-lookup"><span data-stu-id="dff13-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dff13-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="dff13-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="dff13-139">16383</span><span class="sxs-lookup"><span data-stu-id="dff13-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dff13-140">如前所述，為 QoS 設定 Lync Server 埠時，您應該確保：1）音訊埠設定在您的所有會議、應用程式和轉送伺服器上都相同;和，2）埠範圍不會重迭。</span><span class="sxs-lookup"><span data-stu-id="dff13-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="dff13-141">如果您仔細觀察前面的表格，您會看到埠範圍在三種伺服器類型上都是相同的。</span><span class="sxs-lookup"><span data-stu-id="dff13-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="dff13-142">例如，在每個伺服器類型上，啟動音訊埠都設定為 port 49152，而且在每個伺服器上為音訊所保留的埠總數也相同：8348。</span><span class="sxs-lookup"><span data-stu-id="dff13-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="dff13-143">不過，埠的範圍會重迭：音訊埠是從埠49152開始，但會將埠設定為應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="dff13-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="dff13-144">為了讓您能夠最佳地使用服務品質，應該將應用程式共用重新配置為使用唯一的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="dff13-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="dff13-145">例如，您可以將應用程式共用設定為從埠40803開始，並使用8348埠。</span><span class="sxs-lookup"><span data-stu-id="dff13-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="dff13-146">（為什麼要8348埠？</span><span class="sxs-lookup"><span data-stu-id="dff13-146">(Why 8348 ports?</span></span> <span data-ttu-id="dff13-147">如果將這些值加在一起，即 40803 + 8348，即表示應用程式共用將使用埠40803穿過埠49150。</span><span class="sxs-lookup"><span data-stu-id="dff13-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="dff13-148">因為音訊埠無法在埠49152開始，因此您將不會再有任何重迭的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="dff13-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="dff13-149">在您為應用程式共用選取新的埠範圍之後，您可以使用 CsConferencingServer Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="dff13-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="dff13-150">您不需要在應用程式伺服器或您的中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。</span><span class="sxs-lookup"><span data-stu-id="dff13-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="dff13-151">如果您決定要重新指派音訊流量所用的埠，您只需在這些伺服器上變更埠值。</span><span class="sxs-lookup"><span data-stu-id="dff13-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="dff13-152">若要在單一會議服務器上修改應用程式共用的埠值，請在 Lync Server 管理命令介面中執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="dff13-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="dff13-153">如果您想要在所有的會議服務器上進行這些變更，您可以改為執行此命令：</span><span class="sxs-lookup"><span data-stu-id="dff13-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="dff13-154">在變更埠設定之後，您應該停止並重新啟動每個變更所影響的服務。</span><span class="sxs-lookup"><span data-stu-id="dff13-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="dff13-155">您的會議服務器、應用程式伺服器及中繼伺服器共用完全相同的埠範圍，並不是強制性的。唯一的真正需求是您在所有伺服器上都留出唯一的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="dff13-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="dff13-156">不過，如果您在所有伺服器上都使用相同的埠組，系統管理通常會更容易。</span><span class="sxs-lookup"><span data-stu-id="dff13-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

