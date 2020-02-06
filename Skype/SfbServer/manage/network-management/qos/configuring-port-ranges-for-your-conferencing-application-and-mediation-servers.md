---
title: 為您的會議、應用程式和中繼伺服器設定埠範圍及服務品質原則
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何針對您的會議、應用程式及中繼伺服器設定埠範圍及服務品質原則。
ms.openlocfilehash: 76373407a8087e3646668d7ce9952c83c500af97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817442"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="ce200-103">為您的會議、應用程式和中繼伺服器設定埠範圍及服務品質原則</span><span class="sxs-lookup"><span data-stu-id="ce200-103">Configuring port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="ce200-104">本文說明如何針對您的會議、應用程式及中繼伺服器設定埠範圍及服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="ce200-104">This article describes how to configure port ranges and a Quality of Service policy for your Conferencing, Application, and Mediation servers.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="ce200-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="ce200-105">Configure port ranges</span></span>

<span data-ttu-id="ce200-106">若要實現服務品質，您應該在會議、應用程式和中繼伺服器上設定與音訊、影片和應用程式共用相同的埠範圍。此外，這些埠範圍不一定會以任何方式重迭。</span><span class="sxs-lookup"><span data-stu-id="ce200-106">To implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="ce200-107">若要使用簡單的範例，假設您在會議服務器上使用埠10000到10999進行影片。</span><span class="sxs-lookup"><span data-stu-id="ce200-107">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="ce200-108">這表示您也必須在您的應用程式和轉送伺服器上為影片保留埠10000到10999。</span><span class="sxs-lookup"><span data-stu-id="ce200-108">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="ce200-109">否則，QoS 將無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="ce200-109">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="ce200-110">同樣地，假設您將埠10000到10999，以進行影片，但接著將埠10500到11999以進行音訊。</span><span class="sxs-lookup"><span data-stu-id="ce200-110">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="ce200-111">這可能會造成服務品質的問題，因為埠範圍會重迭。</span><span class="sxs-lookup"><span data-stu-id="ce200-111">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="ce200-112">有了 QoS，每個模態都必須擁有一組獨特的埠：如果您使用埠10000到10999進行影片，則必須使用不同的範圍（例如，11000到11999、音訊）。</span><span class="sxs-lookup"><span data-stu-id="ce200-112">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999, for audio).</span></span>

<span data-ttu-id="ce200-113">根據預設，音訊及視訊連接埠範圍不會在商務用 Skype 伺服器中重疊;不過，指派給應用程式共用的埠範圍會與音訊與視訊連接埠範圍重迭。</span><span class="sxs-lookup"><span data-stu-id="ce200-113">By default, audio and video port ranges do not overlap in Skype for Business Server; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="ce200-114">（進而表示這些範圍都不是唯一的）。您可以從商務用 Skype Server Management Shell 中執行下列三個命令，以驗證您的會議、應用程式和轉送作業伺服器的現有埠範圍：</span><span class="sxs-lookup"><span data-stu-id="ce200-114">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Skype for Business Server Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> <span data-ttu-id="ce200-115">您可以在前面的命令中看到，每個埠類型（音訊、影片和應用程式共用）都指派了兩個個別的屬性值：埠開始和埠數。</span><span class="sxs-lookup"><span data-stu-id="ce200-115">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="ce200-116">埠開始指示該模態使用的第一個埠;例如，如果音訊埠開始等於50000，表示音訊流量使用的第一個埠是埠50000。</span><span class="sxs-lookup"><span data-stu-id="ce200-116">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="ce200-117">如果音訊埠數是2（這個值不是有效值，但在這裡是用來做為說明的），則表示只會為音訊指派兩個埠。</span><span class="sxs-lookup"><span data-stu-id="ce200-117">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes), that means that only two ports are allocated for audio.</span></span> <span data-ttu-id="ce200-118">如果第一個埠是埠50000，而且總共有兩個埠，則表示第二個埠必須是埠50001（埠範圍必須是連續的）。</span><span class="sxs-lookup"><span data-stu-id="ce200-118">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="ce200-119">因此，音訊的埠範圍是埠50000到50001（含）。</span><span class="sxs-lookup"><span data-stu-id="ce200-119">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><br><span data-ttu-id="ce200-120">請注意，應用程式伺服器和中繼伺服器只支援音訊的 QoS;您不需要變更應用程式伺服器或轉送伺服器中的影片或應用程式共用埠。</span><span class="sxs-lookup"><span data-stu-id="ce200-120">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>

<span data-ttu-id="ce200-121">如果您執行前面三個命令，您會看到 [商務用 Skype Server] 的預設埠值設定如下：</span><span class="sxs-lookup"><span data-stu-id="ce200-121">If you run the preceding three commands, you'll see that that the default port values for Skype for Business Server are configured like this:</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce200-122">Property</span><span class="sxs-lookup"><span data-stu-id="ce200-122">Property</span></span></th>
<th><span data-ttu-id="ce200-123">會議服務器</span><span class="sxs-lookup"><span data-stu-id="ce200-123">Conferencing Server</span></span></th>
<th><span data-ttu-id="ce200-124">應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="ce200-124">Application Server</span></span></th>
<th><span data-ttu-id="ce200-125">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="ce200-125">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce200-126">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="ce200-126">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="ce200-127">49152</span><span class="sxs-lookup"><span data-stu-id="ce200-127">49152</span></span></p></td>
<td><p><span data-ttu-id="ce200-128">49152</span><span class="sxs-lookup"><span data-stu-id="ce200-128">49152</span></span></p></td>
<td><p><span data-ttu-id="ce200-129">49152</span><span class="sxs-lookup"><span data-stu-id="ce200-129">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce200-130">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="ce200-130">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="ce200-131">8348</span><span class="sxs-lookup"><span data-stu-id="ce200-131">8348</span></span></p></td>
<td><p><span data-ttu-id="ce200-132">8348</span><span class="sxs-lookup"><span data-stu-id="ce200-132">8348</span></span></p></td>
<td><p><span data-ttu-id="ce200-133">8348</span><span class="sxs-lookup"><span data-stu-id="ce200-133">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce200-134">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="ce200-134">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="ce200-135">57501</span><span class="sxs-lookup"><span data-stu-id="ce200-135">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce200-136">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="ce200-136">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="ce200-137">8034</span><span class="sxs-lookup"><span data-stu-id="ce200-137">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce200-138">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="ce200-138">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="ce200-139">49152</span><span class="sxs-lookup"><span data-stu-id="ce200-139">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce200-140">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="ce200-140">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="ce200-141">16383</span><span class="sxs-lookup"><span data-stu-id="ce200-141">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ce200-142">如前所述，在為 QoS 設定商務用 Skype 伺服器埠時，應確定：1）音訊埠設定在您的所有會議、應用程式和轉送伺服器上都相同;和，2）埠範圍不會重迭。</span><span class="sxs-lookup"><span data-stu-id="ce200-142">As noted previously, when configuring Skype for Business Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="ce200-143">如果您仔細觀察前面的表格，您會看到埠範圍在三種伺服器類型上都是相同的。</span><span class="sxs-lookup"><span data-stu-id="ce200-143">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="ce200-144">例如，在每個伺服器類型上，啟動音訊埠都設定為 port 49152，而且在每個伺服器上為音訊所保留的埠總數也相同：8348。</span><span class="sxs-lookup"><span data-stu-id="ce200-144">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="ce200-145">不過，埠的範圍會重迭：音訊埠是從埠49152開始，但會將埠設定為應用程式共用。</span><span class="sxs-lookup"><span data-stu-id="ce200-145">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="ce200-146">為了讓您能夠最佳地使用服務品質，應該將應用程式共用重新配置為使用唯一的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-146">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="ce200-147">例如，您可以將應用程式共用設定為從埠40803開始，並使用8348埠。</span><span class="sxs-lookup"><span data-stu-id="ce200-147">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="ce200-148">（為什麼要8348埠？</span><span class="sxs-lookup"><span data-stu-id="ce200-148">(Why 8348 ports?</span></span> <span data-ttu-id="ce200-149">如果將這些值加在一起，即 40803 + 8348，即表示應用程式共用將使用埠40803穿過埠49150。</span><span class="sxs-lookup"><span data-stu-id="ce200-149">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="ce200-150">因為音訊埠無法在埠49152開始，因此您將不會再有任何重迭的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-150">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="ce200-151">在您為應用程式共用選取新的埠範圍之後，您可以使用 CsConferencingServer Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="ce200-151">After you have selected the new port range for application sharing, you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="ce200-152">您不需要在應用程式伺服器或您的中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。</span><span class="sxs-lookup"><span data-stu-id="ce200-152">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="ce200-153">如果您決定要重新指派音訊流量所用的埠，您只需在這些伺服器上變更埠值。</span><span class="sxs-lookup"><span data-stu-id="ce200-153">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="ce200-154">若要在單一會議服務器上修改應用程式共用的埠值，請在商務用 Skype Server Management Shell 中執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="ce200-154">To modify the port values for application sharing on a single Conferencing server, run a command similar to this from within the Skype for Business Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="ce200-155">如果您想要在所有的會議服務器上進行這些變更，您可以改為執行此命令：</span><span class="sxs-lookup"><span data-stu-id="ce200-155">If you want to make these changes on all your Conferencing servers, you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="ce200-156">在變更埠設定之後，您應該停止並重新啟動每個變更所影響的服務。</span><span class="sxs-lookup"><span data-stu-id="ce200-156">After changing port settings, you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="ce200-157">您的會議服務器、應用程式伺服器及中繼伺服器共用完全相同的埠範圍，並不是強制性的。唯一的真正需求是您在所有伺服器上都留出唯一的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-157">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="ce200-158">不過，如果您在所有伺服器上都使用相同的埠組，系統管理通常會更容易。</span><span class="sxs-lookup"><span data-stu-id="ce200-158">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="ce200-159">在商務用 Skype Server 中針對您的會議、應用程式及中繼伺服器設定品質服務品質原則</span><span class="sxs-lookup"><span data-stu-id="ce200-159">Configure a Quality of Service policy in Skype for Business Server for your Conferencing, Application, and Mediation servers</span></span>

<span data-ttu-id="ce200-160">設定埠範圍的方法是確保指定類型的所有流量（例如，所有音訊流量）都經過同一個埠組，以協助使用服務品質。</span><span class="sxs-lookup"><span data-stu-id="ce200-160">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports.</span></span> <span data-ttu-id="ce200-161">這可讓系統輕鬆識別並標示指定的資料包：如果埠49152是為音訊流量保留，則透過埠49152傳送的任何資料包都可以使用 DSCP 代碼來標示，以表示這是音訊包。</span><span class="sxs-lookup"><span data-stu-id="ce200-161">This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet.</span></span> <span data-ttu-id="ce200-162">接著，這可讓路由器將資料包識別為音訊資料包，並提供比未標記的資料包更高的優先順序（例如，用來將檔案從一個伺服器複製到另一個伺服器的資料包）。</span><span class="sxs-lookup"><span data-stu-id="ce200-162">In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="ce200-163">不過，只要將一組埠限制為特定類型的通信量，就不會導致資料包透過這些埠以適當的 DSCP 代碼標示。</span><span class="sxs-lookup"><span data-stu-id="ce200-163">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="ce200-164">除了定義埠範圍之外，您還必須建立服務原則，以指定要與每個埠範圍相關聯的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="ce200-164">In addition to defining port ranges, you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="ce200-165">針對商務用 Skype Server 而言，這通常表示建立兩個原則：一個用於音訊，另一個用於影片。</span><span class="sxs-lookup"><span data-stu-id="ce200-165">For Skype for Business Server, that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="ce200-166">您可以使用群組原則，輕鬆建立和管理服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="ce200-166">Quality of Service policies are most easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="ce200-167">（您也可以使用本機安全性原則來建立這些相同的原則。</span><span class="sxs-lookup"><span data-stu-id="ce200-167">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="ce200-168">不過，這需要您在每個電腦上重複相同的程式。您最初的 QoS 原則集合（一個用於音訊，另一個用於影片）應該只會套用到執行會議服務器、應用程式伺服器和/或中繼伺服器服務的商務用 Skype 伺服器電腦。</span><span class="sxs-lookup"><span data-stu-id="ce200-168">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Skype for Business Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="ce200-169">如果所有這些電腦都位於同一個 Active Directory OU 中，您可以直接將新的群組原則物件（GPO）指派給該 OU。</span><span class="sxs-lookup"><span data-stu-id="ce200-169">If all of these computers are located in the same Active Directory OU, you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="ce200-170">或者，您也可以採取其他步驟，將新原則的目標設定為指定的電腦;例如，您可以將適當的電腦放在安全群組中，然後使用群組原則安全性篩選，將 GPO 只套用到該安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ce200-170">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="ce200-171">若要建立用來管理音訊的服務品質原則，請登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="ce200-171">To create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="ce200-172">開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="ce200-172">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="ce200-173">在 [群組原則管理] 中，找出要建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="ce200-173">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="ce200-174">例如，如果您所有的商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="ce200-174">For example, if all your Skype for Business Server computers are located in an OU named Skype for Business Server, then the new policy should be created in the Skype for Business Server OU.</span></span>

2.  <span data-ttu-id="ce200-175">以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域建立 GPO]，然後在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="ce200-175">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="ce200-176">在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如商務用**Skype Server QoS**），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-176">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Skype for Business Server QoS**), and then click **OK**.</span></span>

4.  <span data-ttu-id="ce200-177">以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-177">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="ce200-178">在 [群組原則管理編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-178">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="ce200-179">在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**商務用 Skype Server QoS**）。</span><span class="sxs-lookup"><span data-stu-id="ce200-179">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Skype for Business Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="ce200-180">選取 [**指定 DSCP 值**]，然後將值設定為**46**。</span><span class="sxs-lookup"><span data-stu-id="ce200-180">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="ce200-181">[離開]**指定輸出限制率**未選取，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-181">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="ce200-182">在下一頁上，確認已選取 [**所有應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-182">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="ce200-183">這只會確保所有應用程式都能將來自指定埠範圍的資料包與指定的 DSCP 代碼相符。</span><span class="sxs-lookup"><span data-stu-id="ce200-183">This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="ce200-184">在第三個頁面上，確認已選取 [**所有來源 ip 位址] 和 [任何目的地 ip 位址**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-184">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="ce200-185">這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。</span><span class="sxs-lookup"><span data-stu-id="ce200-185">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="ce200-186">在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。</span><span class="sxs-lookup"><span data-stu-id="ce200-186">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="ce200-187">TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是商務用 Skype Server 及其用戶端應用程式最常用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="ce200-187">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="ce200-188">在 [標題] 底下，**指定來源埠號**，選取 [**從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-188">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="ce200-189">在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-189">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="ce200-190">例如，如果您是透過埠57500將埠49152保留音訊流量，請輸入使用此格式的埠範圍： **49152:57500**。</span><span class="sxs-lookup"><span data-stu-id="ce200-190">For example, if you reserved ports 49152 through ports 57500 for audio traffic, enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="ce200-191">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-191">Click **Finish**.</span></span>

> [!NOTE]  
> <span data-ttu-id="ce200-192">46的 DSCP 值有點隨意：雖然 DSCP 46 通常是用來標示音訊資料包，但您不需要使用 DSCP 46 進行音訊通訊。</span><span class="sxs-lookup"><span data-stu-id="ce200-192">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications.</span></span> <span data-ttu-id="ce200-193">如果您已經實現 QoS，且您使用的是不同的音訊 DSCP 代碼（例如，DSCP 40），您應該將服務品質原則設定為使用相同的程式碼（亦即，40的音訊）。</span><span class="sxs-lookup"><span data-stu-id="ce200-193">If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40), you should configure your Quality of Service policy to use that same code (i.e., 40 for audio).</span></span> <span data-ttu-id="ce200-194">如果您只是在執行服務品質，建議您將 DSCP 46 用於音訊，只要這個值通常是用來標示音訊資料包就好了。</span><span class="sxs-lookup"><span data-stu-id="ce200-194">If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>

<span data-ttu-id="ce200-195">在您建立音訊流量的 QoS 原則之後，您應該接著建立影片流量的第二個原則（也就是用於管理應用程式共用流量的第三個原則）。</span><span class="sxs-lookup"><span data-stu-id="ce200-195">After you have created the QoS policy for audio traffic, you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic).</span></span> <span data-ttu-id="ce200-196">若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：</span><span class="sxs-lookup"><span data-stu-id="ce200-196">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="ce200-197">使用不同（且唯一的）原則名稱（例如商務用**Skype Server 影片**）。</span><span class="sxs-lookup"><span data-stu-id="ce200-197">Use a different (and unique) policy name (for example, **Skype for Business Server Video**).</span></span>

  - <span data-ttu-id="ce200-198">將 DSCP 值設為**34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="ce200-198">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="ce200-199">（請注意，您不需要使用34的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="ce200-199">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="ce200-200">唯一的需求是，您針對影片使用的 DSCP 值與音訊所用的不同。</span><span class="sxs-lookup"><span data-stu-id="ce200-200">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="ce200-201">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-201">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ce200-202">例如，如果您已將埠57501到65535的備用，請將埠範圍設定為： **57501:65535**。</span><span class="sxs-lookup"><span data-stu-id="ce200-202">For example, if you have reserved ports 57501 through 65535 for video, set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="ce200-203">如果您決定建立用來管理應用程式共用流量的原則，您必須建立第三個原則，以進行下列替換：</span><span class="sxs-lookup"><span data-stu-id="ce200-203">If you decide to create a policy for managing application sharing traffic, you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="ce200-204">使用不同（且唯一的）原則名稱（例如，**商務用 Skype Server 應用程式共用**）。</span><span class="sxs-lookup"><span data-stu-id="ce200-204">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="ce200-205">將 DSCP 值設為**24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="ce200-205">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="ce200-206">（同樣地，您不需要使用 DSCP 值24。</span><span class="sxs-lookup"><span data-stu-id="ce200-206">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="ce200-207">唯一的需求是，您針對與音訊或影片搭配使用的應用程式共用，使用不同的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="ce200-207">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="ce200-208">使用先前設定的影片流量埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ce200-208">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="ce200-209">例如，如果您已在應用程式共用中保留埠40803到49151，請將埠範圍設定為： **40803:49151**。</span><span class="sxs-lookup"><span data-stu-id="ce200-209">For example, if you have reserved ports 40803 through 49151 for application sharing, set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="ce200-210">您建立的新原則必須在您的商務用 Skype Server 電腦上重新整理群組原則之後，才會生效。</span><span class="sxs-lookup"><span data-stu-id="ce200-210">The new policies you have created will not take effect until Group Policy has been refreshed on your Skype for Business Server computers.</span></span> <span data-ttu-id="ce200-211">雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="ce200-211">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="ce200-212">此命令可以從商務用 Skype Server Management 命令介面或從任何執行的命令視窗在 [管理員認證] 下執行。</span><span class="sxs-lookup"><span data-stu-id="ce200-212">This command can be run from within the Skype for Business Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="ce200-213">若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="ce200-213">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="ce200-214">若要確認已套用新的 QoS 原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ce200-214">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="ce200-215">在商務用 Skype Server 電腦上，按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-215">On a Skype for Business Server computer, click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ce200-216">在 [**執行**] 對話方塊中，輸入**regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="ce200-216">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ce200-217">在 [登錄編輯程式] 中，展開 [**電腦**]，展開 [ \*\* \_HKEY 本機\_電腦**]，展開 [**軟體**]，然後展開 [**原則**]、[ **Microsoft**]、[ **Windows**]，**然後按一下 [\*\*</span><span class="sxs-lookup"><span data-stu-id="ce200-217">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="ce200-218">在 [ **QoS** ] 底下，您應該會看到您剛建立的每一個 QoS 原則的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="ce200-218">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="ce200-219">例如，如果您已建立兩個新的原則（一個名為商務用 skype server Audio QoS，以及其他已命名的商務用 Skype Server Video QoS），您應該會看到商務用 Skype Server 音訊 QoS 和商務用 Skype Server 影片的登錄專案。</span><span class="sxs-lookup"><span data-stu-id="ce200-219">For example, if you created two new policies (one named Skype for Business Server Audio QoS and the other named Skype for Business Server Video QoS), you should see registry entries for Skype for Business Server Audio QoS and Skype for Business Server Video QoS.</span></span>

<span data-ttu-id="ce200-220">若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：</span><span class="sxs-lookup"><span data-stu-id="ce200-220">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="ce200-221">按一下 [**開始**]，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-221">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="ce200-222">在 [**執行**] 對話方塊中，輸入**regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="ce200-222">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="ce200-223">在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-223">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="ce200-224">以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-224">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="ce200-225">建立新的登錄金鑰之後，請輸入**QoS**，然後按 enter 來重新命名金鑰。</span><span class="sxs-lookup"><span data-stu-id="ce200-225">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="ce200-226">以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-226">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="ce200-227">建立新的登錄值之後，請輸入 [**不使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="ce200-227">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ce200-228">按兩下 [**不使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="ce200-228">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="ce200-229">在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce200-229">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ce200-230">關閉 [登錄編輯程式]，然後重新開機您的電腦。</span><span class="sxs-lookup"><span data-stu-id="ce200-230">Close the Registry Editor and reboot your computer.</span></span>
