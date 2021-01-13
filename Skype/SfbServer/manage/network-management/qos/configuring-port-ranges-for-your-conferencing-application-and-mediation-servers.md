---
title: 針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則。
ms.openlocfilehash: 8c65e36528615aca181b6aac17aab844c1a4d206
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800123"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="ad5d8-103">針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則</span><span class="sxs-lookup"><span data-stu-id="ad5d8-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="ad5d8-104">本文說明如何針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="ad5d8-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="ad5d8-105">Configure port ranges</span></span>

<span data-ttu-id="ad5d8-106">若要執行服務品質，您應該針對會議、應用程式及轉送伺服器上的音訊、影片和應用程式共用，設定相同的埠範圍。此外，這些埠範圍不得以任何方式重疊。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="ad5d8-107">舉個簡單的例子，假設您針對會議伺服器上的視訊使用連接埠 10000 到 10999。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="ad5d8-108">這表示您也必須為應用程式和中繼伺服器上的視訊保留連接埠 10000 到 10999。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="ad5d8-109">如果沒有，服務品質 (QoS) 將無法如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="ad5d8-110">同樣地，假設您為視訊保留連接埠 10000 到 10999，但接著為音訊保留連接埠 10500 到 11999。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="ad5d8-111">這樣會造成服務品質的問題，因為連接埠範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="ad5d8-112">在 QoS 中，每個模態都必須有一組獨特的埠：如果您使用埠10000到10999以進行影片，則必須使用不同的範圍 (（例如11000到11999，針對音訊) ）。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="ad5d8-113">依預設，在商務用 Skype Server 中，音訊和視訊連接埠範圍不會重疊;不過，指派給應用程式共用的埠範圍會與音訊和視訊連接埠範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="ad5d8-114"> (它會反過來表示這些範圍都不是唯一的。 ) 您可以從商務用 Skype Server 管理命令介面執行下列三個命令，以驗證會議、應用程式及轉送伺服器的現有埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="ad5d8-115">如同您在上述命令中所見，每一種連接埠類型 (音訊、視訊和應用程式共用) 都會被指派兩個不同的屬性值：連接埠起點和連接埠計數。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="ad5d8-116">連接埠起點指出用於該形式的第一個連接埠；例如，如果音訊連接埠起點等於 50000，表示用於音訊流量的第一個連接埠是連接埠 50000。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="ad5d8-117">如果音訊埠計數為 2 (不是有效值，但在這裡是用來做說明，請) ，這表示只有兩個埠為音訊所指派。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="ad5d8-118">如果第一個連接埠是連接埠 50000，且總共有兩個連接埠，表示第二個連接埠一定是連接埠 50001 (連接埠範圍必須是連續的)。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="ad5d8-119">因此，音訊的連接埠範圍將會是連接埠 50000 到 50001 (含)。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="ad5d8-120">另請注意，應用程式伺服器和中繼伺服器只支援音訊的服務品質；您不需要在應用程式伺服器或中繼伺服器中變更視訊或應用程式共用連接埠。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="ad5d8-121">如果您執行上述三個命令，您會看到商務用 Skype Server 的預設埠值是設定如下：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad5d8-122">屬性	</span><span class="sxs-lookup"><span data-stu-id="ad5d8-122">Property</span></span></th>
<th><span data-ttu-id="ad5d8-123">會議伺服器</span><span class="sxs-lookup"><span data-stu-id="ad5d8-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="ad5d8-124">應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="ad5d8-124">Application Server</span></span></th>
<th><span data-ttu-id="ad5d8-125">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="ad5d8-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad5d8-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="ad5d8-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-127">49152</span><span class="sxs-lookup"><span data-stu-id="ad5d8-127">49152</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-128">49152</span><span class="sxs-lookup"><span data-stu-id="ad5d8-128">49152</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-129">49152</span><span class="sxs-lookup"><span data-stu-id="ad5d8-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad5d8-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="ad5d8-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-131">8348</span><span class="sxs-lookup"><span data-stu-id="ad5d8-131">8348</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-132">8348</span><span class="sxs-lookup"><span data-stu-id="ad5d8-132">8348</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-133">8348</span><span class="sxs-lookup"><span data-stu-id="ad5d8-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad5d8-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="ad5d8-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-135">57501</span><span class="sxs-lookup"><span data-stu-id="ad5d8-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad5d8-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="ad5d8-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-137">8034</span><span class="sxs-lookup"><span data-stu-id="ad5d8-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad5d8-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="ad5d8-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-139">49152</span><span class="sxs-lookup"><span data-stu-id="ad5d8-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad5d8-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="ad5d8-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="ad5d8-141">16383</span><span class="sxs-lookup"><span data-stu-id="ad5d8-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ad5d8-142">如先前所述，設定 QoS 的商務用 Skype 伺服器埠時，應確定： 1) 音訊埠設定在您的會議、應用程式及轉送伺服器上都相同。而且，2) 埠範圍不會重疊。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="ad5d8-143">如果您仔細查看前面的表格，您會看到埠範圍在三個伺服器類型中皆相同。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="ad5d8-144">例如，在每個伺服器類型上，啟動音訊埠設定為埠49152，而在每個伺服器上為音訊保留的埠總數也相同：8348。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="ad5d8-145">不過，埠範圍會重迭：音訊埠會從埠49152開始，但也會為應用程式共用設定埠。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="ad5d8-146">為了讓服務品質獲得最佳的使用，應將應用程式共用重新設定為使用唯一的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="ad5d8-147">例如，您可以將應用程式共用設定為從埠40803開始，並使用8348埠。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="ad5d8-148"> (為何8348埠？</span><span class="sxs-lookup"><span data-stu-id="ad5d8-148">(Why 8348 ports?</span></span> <span data-ttu-id="ad5d8-149">如果您將這些值一起新增--40803 + 8348--這表示應用程式共用將使用埠40803透過埠49150。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="ad5d8-150">因為音訊埠不會開始，直到埠49152，您就不會再有任何重疊的埠範圍。 ) </span><span class="sxs-lookup"><span data-stu-id="ad5d8-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="ad5d8-151">選取應用程式共用的新埠範圍後，您可以使用 Set-CsConferencingServer Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="ad5d8-152">您不需要在應用程式伺服器或中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="ad5d8-153">如果您決定要重新指派用於音效流量的連接埠，只要在這些伺服器上變更連接埠值即可。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="ad5d8-154">若要在單一會議服務器上修改應用程式共用的埠值，請在商務用 Skype Server 管理命令介面中執行類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="ad5d8-155">如果您想要在所有會議服務器上進行這些變更，可以改為執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="ad5d8-156">變更埠設定之後，您應該停止並重新啟動每個變更所影響的服務。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="ad5d8-p107">您的會議伺服器、應用程式伺服器和中繼伺服器並不是一定要共用完全相同的連接埠範圍；唯一必要的需求是您要在所有的伺服器上預留唯一的連接埠範圍。不過，如果您在所有伺服器上使用同一組連接埠，通常會讓管理工作更為輕鬆。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="ad5d8-159">針對會議、應用程式及轉送伺服器設定商務用 Skype Server 中的服務品質原則</span><span class="sxs-lookup"><span data-stu-id="ad5d8-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="ad5d8-160">設定埠範圍可確保指定類型的所有流量 (，以協助使用服務品質。例如，所有音訊流量) 一組相同的埠。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="ad5d8-161">這可讓系統輕鬆識別及標記指定的封包：如果為音訊流量保留埠49152，則透過埠49152的任何封包都會以 DSCP 代碼標示，表示這是音訊封包。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="ad5d8-162">反過來，這可讓路由器將封包識別為音訊封包，並提供比未標記的封包更高的優先順序 (例如，用來將檔案從一部伺服器複製到另一個) 的封包。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="ad5d8-163">不過，只要將一組埠限制在特定類型的流量中，就不會導致透過以適當 DSCP 代碼標示的埠傳送傳輸。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="ad5d8-164">除了定義埠範圍之外，您還必須建立服務原則的品質，指定要與每個埠範圍相關聯的 DSCP 碼。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="ad5d8-165">若為商務用 Skype Server，通常表示建立兩個原則：一個用於音訊，另一個用於影片。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="ad5d8-166">使用群組原則，可很輕鬆地建立及管理服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="ad5d8-167">您也可以使用本機安全性原則建立這些相同原則 (。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="ad5d8-168">不過，您必須在每個電腦和每一部電腦上重複相同的程式。 ) 您的初始 QoS 原則集合 (一個用於音訊，另一個用於影片) 只適用于執行會議服務器、應用程式伺服器及/或轉送伺服器服務的商務用 Skype 伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="ad5d8-169">如果所有這些電腦都位於相同的 Active Directory OU 中，您可以只指派新的群組原則物件 (GPO) 給該 OU。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="ad5d8-170">或者，您也可以執行其他步驟，將新的原則設定為指定的電腦;例如，您可以將適當的電腦放在安全性群組中，然後使用群組原則安全性篩選，將 GPO 只套用到該安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="ad5d8-171">若要建立服務品質原則以管理音訊，請登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="ad5d8-172">開啟群組原則管理 (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理** ]) 然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="ad5d8-173">在群組原則管理中，找出要用來建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="ad5d8-174">例如，如果您所有的商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="ad5d8-175">以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="ad5d8-176">在 [ **新增 GPO** ] 對話方塊的 [ **名稱** ] 方塊中，輸入新群組原則物件的名稱 (例如， **商務用 Skype Server QoS**) ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="ad5d8-177">以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="ad5d8-178">在 [群組原則管理編輯器] 中，依序展開 [ **電腦** 設定] 及 [ **原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [ **原則] QoS**，然後按一下 [ **建立新原則**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="ad5d8-179">在 [**原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱 (例如，**商務用 Skype Server QoS**) 。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="ad5d8-180">選取 [指定 DSCP 數值]，並將該值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="ad5d8-181">將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="ad5d8-182">在下一個頁面上，確定已選取 [ **所有應用程式** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="ad5d8-183">這只是確保所有應用程式會與指定的 DSCP 碼從指定的埠範圍中的封包相符。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="ad5d8-184">在第三頁上，確定已選取 [ **所有來源 ip 位址] 和 [任何目的地 ip 位址** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="ad5d8-185">這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="ad5d8-186">在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="ad5d8-187">TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="ad5d8-188">在 [標題] 中 **指定來源埠號碼**，選取 [ **從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="ad5d8-189">在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="ad5d8-190">例如，如果您將埠49152設定為音訊流量的埠57500，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="ad5d8-191">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="ad5d8-192">46的 DSCP 值有點隨意：雖然 DSCP 46 通常是用來標示音訊封包，但您不需要使用 DSCP 46 進行音訊通訊。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="ad5d8-193">如果您已執行 QoS，而且您使用的是不同的 DSCP 碼來進行音訊 (例如，DSCP 40) ，則應該設定您的服務品質原則，以使用相同的程式碼 (例如，40的音訊) 。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="ad5d8-194">如果您現在只是實施服務品質，建議您將 DSCP 46 用於音訊，只是因為此值通常是用來標示音訊封包。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="ad5d8-195">在您建立音訊流量的 QoS 原則之後，您應該先為影片流量建立第二個原則 (並選擇性地，第三個用於管理應用程式共用流量) 的原則。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="ad5d8-196">若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="ad5d8-197">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 影片**) 。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="ad5d8-p120">將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)</span><span class="sxs-lookup"><span data-stu-id="ad5d8-p120">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="ad5d8-201">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ad5d8-202">例如，如果您有保留的埠57501到65535以取得影片，請將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="ad5d8-203">如果您決定建立用來管理應用程式共用流量的原則，則必須建立第三個原則，以進行下列替代：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="ad5d8-204">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 應用程式共用**) 。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="ad5d8-p122">將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)</span><span class="sxs-lookup"><span data-stu-id="ad5d8-p122">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="ad5d8-208">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ad5d8-209">例如，如果您有保留埠40803到49151以進行應用程式共用，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="ad5d8-210">在您的商務用 Skype Server 電腦上重新整理群組原則後，您建立的新原則將不會生效。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="ad5d8-211">雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="ad5d8-212">您可以從商務用 Skype Server 管理命令介面或任何執行于系統管理員認證的命令視窗中執行此命令。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="ad5d8-213">若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="ad5d8-214">若要確認已套用新的 QoS 原則，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="ad5d8-215">在商務用 Skype Server 電腦上，按一下 [ **開始**]，然後按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ad5d8-216">在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ad5d8-217">在登錄編輯程式中，依序展開 [ **電腦**]、[ **HKEY \_ 本機 \_ 電腦**]、[ **軟體**]、[ **原則**] 及 [ **Microsoft**]，展開 [ **Windows**]，然後按一下 [ **QoS**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="ad5d8-218">在 [ **QoS** 您應該會看到您剛才建立之每個 QoS 原則的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="ad5d8-219">例如，如果您建立兩個新的原則 (一個名為商務用 Skype Server 音訊 QoS，另一個名為商務用 Skype Server 影片 QoS) ，您應該會看到商務用 Skype Server 音訊 QoS 和商務用 Skype Server 影片 QoS 的登錄專案。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="ad5d8-220">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="ad5d8-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="ad5d8-221">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ad5d8-222">在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ad5d8-223">在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="ad5d8-224">以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="ad5d8-225">在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="ad5d8-226">以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="ad5d8-227">在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ad5d8-228">按兩下 [ **不要使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="ad5d8-229">在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ad5d8-230">關閉 [登錄編輯程式]，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="ad5d8-230">Close the Registry Editor and reboot your computer.</span></span>
