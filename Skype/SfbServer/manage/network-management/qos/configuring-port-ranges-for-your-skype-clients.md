---
title: 為用戶端設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
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
description: 本文說明如何為您的用戶端設定埠範圍，以及如何為在 Windows 10 上執行的用戶端在商務用 Skype Server 中設定服務品質原則。
ms.openlocfilehash: 9cd5fe3fa84c4acd9365e02c0e5801b63d5497d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122427"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="175c5-103">為商務用 Skype Server 中的用戶端設定埠範圍和服務品質原則</span><span class="sxs-lookup"><span data-stu-id="175c5-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="175c5-104">本文說明如何為您的用戶端設定埠範圍，以及如何為在 Windows 10 上執行的用戶端在商務用 Skype Server 中設定服務品質原則。</span><span class="sxs-lookup"><span data-stu-id="175c5-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="175c5-105">設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="175c5-105">Configure port ranges</span></span>

<span data-ttu-id="175c5-106">根據預設，商務用 Skype 用戶端應用程式可以使用埠1024和65535之間的任何埠，與通訊會話相關;這是因為不會自動為用戶端啟用特定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="175c5-107">然而為了使用服務品質，您必須將各種流量類型重新分派 (音訊、視訊、媒體、應用程式共用及檔案傳輸) 至一系列的唯一連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="175c5-108">使用 Set-CsConferencingConfiguration Cmdlet 可達成此目的。</span><span class="sxs-lookup"><span data-stu-id="175c5-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="175c5-109">使用者無法自行進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="175c5-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="175c5-110">只有管理員使用 Set-CsConferencingConfiguration Cmdlet 才能進行埠變更。</span><span class="sxs-lookup"><span data-stu-id="175c5-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="175c5-111">您可以從商務用 Skype Server 管理命令介面中執行下列命令，判斷目前用於通訊會話的埠範圍：</span><span class="sxs-lookup"><span data-stu-id="175c5-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="175c5-112">假設您在安裝商務用 Skype Server 後，尚未對會議設定進行任何變更，您應該會收到包含下列屬性值的資訊：</span><span class="sxs-lookup"><span data-stu-id="175c5-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="175c5-113">若您仔細看前面的輸出，就會注意到兩項重點。</span><span class="sxs-lookup"><span data-stu-id="175c5-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="175c5-114">首先，ClientMediaPortRangeEnabled 屬性是設為 False：</span><span class="sxs-lookup"><span data-stu-id="175c5-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="175c5-115">這一點很重要，因為當此屬性設定為 False 時，商務用 Skype 用戶端會在通訊會話中時使用埠1024和65535之間的任何可用埠;不論任何其他埠設定 (例如，ClientMediaPort 或 ClientVideoPort) ，都是如此。</span><span class="sxs-lookup"><span data-stu-id="175c5-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="175c5-116">如果您想要將使用限制在一組指定的埠 (，而這是您在規劃執行服務品質) 時所要執行的動作，則必須先啟用用戶端媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="175c5-117">可以使用下列 Windows PowerShell 命令來完成：</span><span class="sxs-lookup"><span data-stu-id="175c5-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="175c5-p105">前面的命令會啟用全域會議組態設定集合的用戶端媒體連接埠；不過這些設定也可套用至網站範圍及/或服務範圍 (僅限會議伺服器服務)。若要啟用特定網站或伺服器的用戶端媒體連接埠範圍，請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的識別：</span><span class="sxs-lookup"><span data-stu-id="175c5-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="175c5-120">或者，您也可使用此命令，同時啟用所有會議組態設定的連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="175c5-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="175c5-121">您注意到的第二項重點是範例輸出顯示，根據預設，針對每個網路流量類型所設定的媒體連接埠範圍皆為相同：</span><span class="sxs-lookup"><span data-stu-id="175c5-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="175c5-p106">為了實作 QoS，其中的每個連接埠範圍皆必須是唯一的連接埠範圍。例如，您可能設定了如下的連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="175c5-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="175c5-124">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="175c5-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="175c5-125">連接埠開始</span><span class="sxs-lookup"><span data-stu-id="175c5-125">Port Start</span></span></th>
<th><span data-ttu-id="175c5-126">連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="175c5-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="175c5-127">音訊</span><span class="sxs-lookup"><span data-stu-id="175c5-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="175c5-128">50020</span><span class="sxs-lookup"><span data-stu-id="175c5-128">50020</span></span></p></td>
<td><p><span data-ttu-id="175c5-129">共</span><span class="sxs-lookup"><span data-stu-id="175c5-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175c5-130">影片</span><span class="sxs-lookup"><span data-stu-id="175c5-130">Video</span></span></p></td>
<td><p><span data-ttu-id="175c5-131">58000</span><span class="sxs-lookup"><span data-stu-id="175c5-131">58000</span></span></p></td>
<td><p><span data-ttu-id="175c5-132">共</span><span class="sxs-lookup"><span data-stu-id="175c5-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175c5-133">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="175c5-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="175c5-134">42000</span><span class="sxs-lookup"><span data-stu-id="175c5-134">42000</span></span></p></td>
<td><p><span data-ttu-id="175c5-135">共</span><span class="sxs-lookup"><span data-stu-id="175c5-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175c5-136">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="175c5-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="175c5-137">42020</span><span class="sxs-lookup"><span data-stu-id="175c5-137">42020</span></span></p></td>
<td><p><span data-ttu-id="175c5-138">共</span><span class="sxs-lookup"><span data-stu-id="175c5-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="175c5-139">在上表中，用戶端埠範圍代表為您的伺服器設定的埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="175c5-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="175c5-140">例如，在伺服器上，應用程式共用設定為使用埠40803到 49151;在用戶端電腦上，應用程式共用設定為使用埠42000到42019。</span><span class="sxs-lookup"><span data-stu-id="175c5-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="175c5-141">這樣做也主要是為了簡化 QoS 的管理：用戶端埠不一定要代表伺服器上使用的埠子集。</span><span class="sxs-lookup"><span data-stu-id="175c5-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="175c5-142"> (例如，在用戶端電腦上，您可以設定要使用的應用程式共用，比如說，埠10000到10019。 ) 不過，建議您讓用戶端埠範圍成為伺服器埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="175c5-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="175c5-143">此外，您可能還有注意到，在伺服器上針對應用程式共用獨立設定了 8348 個連接埠，但用戶端上的應用程式共用僅獨立設定了 20 個連接埠。</span><span class="sxs-lookup"><span data-stu-id="175c5-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="175c5-144">建議您也這麼做，但不是一種很快的規則。</span><span class="sxs-lookup"><span data-stu-id="175c5-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="175c5-145">一般說來，您可以將每個可用的埠視為代表單一通訊會話：如果埠範圍中有100埠可供使用，這表示有問題的電腦在任何指定時間內最多可加入100通訊會話。</span><span class="sxs-lookup"><span data-stu-id="175c5-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="175c5-146">因為伺服器可能會比用戶端參與更多的交談，所以在伺服器上開啟比用戶端更多的連接埠也很合理。</span><span class="sxs-lookup"><span data-stu-id="175c5-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="175c5-147">為應用程式共用在用戶端上獨立設定 20 個連接埠，表示使用者可在特定裝置上同時參與 20 個應用程式共用工作階段。</span><span class="sxs-lookup"><span data-stu-id="175c5-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="175c5-148">這對於您絕大多數的使用者而言應該已足夠使用。</span><span class="sxs-lookup"><span data-stu-id="175c5-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="175c5-149">若要將先前的埠範圍指派給全域會議設定的集合，您可以使用下列商務用 Skype Server 管理命令介面命令：</span><span class="sxs-lookup"><span data-stu-id="175c5-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="175c5-150">或是使用此命令將這些相同的連接埠範圍指派給所有會議組態設定：</span><span class="sxs-lookup"><span data-stu-id="175c5-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="175c5-151">個別使用者必須從商務用 Skype 登出，然後重新登入，這些變更實際會生效。</span><span class="sxs-lookup"><span data-stu-id="175c5-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="175c5-152">您也可以啟用用戶端媒體埠範圍，然後使用單一命令指派這些埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="175c5-153">例如：</span><span class="sxs-lookup"><span data-stu-id="175c5-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="175c5-154">設定在 Windows 10 上執行之用戶端的服務品質原則</span><span class="sxs-lookup"><span data-stu-id="175c5-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="175c5-155">除了指定商務用 Skype 用戶端所使用的埠範圍之外，還必須建立要套用至用戶端電腦的個別服務原則品質。</span><span class="sxs-lookup"><span data-stu-id="175c5-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="175c5-156"> (針對會議、應用程式及轉送伺服器建立的服務原則的品質不應該套用至用戶端電腦。 ) 此資訊僅適用于執行商務用 Skype 用戶端和 Windows 10 的電腦。</span><span class="sxs-lookup"><span data-stu-id="175c5-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="175c5-157">下列範例會使用這組埠範圍來建立音訊原則和影片原則：</span><span class="sxs-lookup"><span data-stu-id="175c5-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="175c5-158">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="175c5-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="175c5-159">連接埠開始</span><span class="sxs-lookup"><span data-stu-id="175c5-159">Port Start</span></span></th>
<th><span data-ttu-id="175c5-160">連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="175c5-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="175c5-161">音訊</span><span class="sxs-lookup"><span data-stu-id="175c5-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="175c5-162">50020</span><span class="sxs-lookup"><span data-stu-id="175c5-162">50020</span></span></p></td>
<td><p><span data-ttu-id="175c5-163">共</span><span class="sxs-lookup"><span data-stu-id="175c5-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175c5-164">影片</span><span class="sxs-lookup"><span data-stu-id="175c5-164">Video</span></span></p></td>
<td><p><span data-ttu-id="175c5-165">58000</span><span class="sxs-lookup"><span data-stu-id="175c5-165">58000</span></span></p></td>
<td><p><span data-ttu-id="175c5-166">共</span><span class="sxs-lookup"><span data-stu-id="175c5-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="175c5-167">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="175c5-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="175c5-168">42000</span><span class="sxs-lookup"><span data-stu-id="175c5-168">42000</span></span></p></td>
<td><p><span data-ttu-id="175c5-169">共</span><span class="sxs-lookup"><span data-stu-id="175c5-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175c5-170">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="175c5-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="175c5-171">42020</span><span class="sxs-lookup"><span data-stu-id="175c5-171">42020</span></span></p></td>
<td><p><span data-ttu-id="175c5-172">共</span><span class="sxs-lookup"><span data-stu-id="175c5-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="175c5-173">若要為 Windows 10 電腦建立服務品質音訊原則，請先登入已安裝群組原則管理的電腦。</span><span class="sxs-lookup"><span data-stu-id="175c5-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="175c5-174">開啟群組原則管理 (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理**) ]，然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="175c5-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="175c5-175">在群組原則管理中，找出要用來建立新原則的容器。</span><span class="sxs-lookup"><span data-stu-id="175c5-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="175c5-176">例如，如果所有用戶端電腦都位於名為用戶端的 OU 中，則應該在用戶端 OU 中建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="175c5-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="175c5-177">以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。</span><span class="sxs-lookup"><span data-stu-id="175c5-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="175c5-178">在 [ **新增 GPO** ] 對話方塊的 [ **名稱** ] 方塊中，輸入新群組原則物件的名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="175c5-179">以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="175c5-180">在 [群組原則管理編輯器] 中，展開 [ **電腦** 設定]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [ **原則] QoS**，然後按一下 [ **建立新原則**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="175c5-181">在 [ **原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [ **名稱** ] 方塊中輸入新原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="175c5-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="175c5-182">選取 [指定 DSCP 數值]，並將該值設為 **46**。</span><span class="sxs-lookup"><span data-stu-id="175c5-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="175c5-183">將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="175c5-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="175c5-184">在下一個頁面上，選取 [ **僅限具有此可執行檔名稱的應用程式**]，輸入 **Lync.exe** 作為名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="175c5-185">此設定指示原則僅優先于商務用 Skype 用戶端的相符流量。</span><span class="sxs-lookup"><span data-stu-id="175c5-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="175c5-186">在第三頁上，確定已選取 [ **所有來源 ip 位址** ] 和 [ **任何目的地 ip 位址** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="175c5-187">這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。</span><span class="sxs-lookup"><span data-stu-id="175c5-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="175c5-188">在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。</span><span class="sxs-lookup"><span data-stu-id="175c5-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="175c5-189">TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。</span><span class="sxs-lookup"><span data-stu-id="175c5-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="175c5-190">在 [標題] 中 **指定來源埠號碼**，選取 [ **從此來源埠或範圍**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="175c5-191">在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="175c5-192">例如，如果您使用埠50020經由埠50039進行音訊流量，請輸入使用此格式的埠範圍： **50020:50039**。</span><span class="sxs-lookup"><span data-stu-id="175c5-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="175c5-193">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-193">Click **Finish**.</span></span>

<span data-ttu-id="175c5-194">建立音訊的 QoS 原則之後，您應該先建立影片的第二個原則。</span><span class="sxs-lookup"><span data-stu-id="175c5-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="175c5-195">若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：</span><span class="sxs-lookup"><span data-stu-id="175c5-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="175c5-196">使用不同的 (和唯一的) 原則名稱。</span><span class="sxs-lookup"><span data-stu-id="175c5-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="175c5-197">將 DSCP 值設定為 **34** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="175c5-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="175c5-198"> (如先前所述，您不需要使用 DSCP 值 34;您只須指派不同于音訊使用的 DSCP 值。 ) </span><span class="sxs-lookup"><span data-stu-id="175c5-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="175c5-199">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="175c5-200">例如，如果您有保留的埠58000到58019以取得影片，請將埠範圍設定為： **58000:58019**。</span><span class="sxs-lookup"><span data-stu-id="175c5-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="175c5-201">如果您決定建立原則以管理應用程式共用流量，請進行下列的替代專案：</span><span class="sxs-lookup"><span data-stu-id="175c5-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="175c5-202">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 應用程式共用**) 。</span><span class="sxs-lookup"><span data-stu-id="175c5-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="175c5-203">將 DSCP 值設定為 **24** ，而不是46。</span><span class="sxs-lookup"><span data-stu-id="175c5-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="175c5-204"> (此外，此值不必為 24;它只必須不同于音訊和影片所用的 DSCP 值。 ) </span><span class="sxs-lookup"><span data-stu-id="175c5-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="175c5-205">使用先前設定的影片流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="175c5-206">例如，如果您有保留埠42000到42019以進行應用程式共用，請將埠範圍設定為： **42000:42019**。</span><span class="sxs-lookup"><span data-stu-id="175c5-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="175c5-207">對於檔案傳輸原則：</span><span class="sxs-lookup"><span data-stu-id="175c5-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="175c5-208">使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server** 檔案會) 傳輸。</span><span class="sxs-lookup"><span data-stu-id="175c5-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="175c5-209">將 DSCP 值設定為 **14**。</span><span class="sxs-lookup"><span data-stu-id="175c5-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="175c5-210"> (此外，此值不必為 14;它只必須是唯一的 DSCP 代碼。 ) </span><span class="sxs-lookup"><span data-stu-id="175c5-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="175c5-211">針對應用程式使用先前設定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="175c5-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="175c5-212">例如，如果您有保留埠42020到42039以進行應用程式共用，請將埠範圍設定為： **42020:42039**。</span><span class="sxs-lookup"><span data-stu-id="175c5-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="175c5-213">在用戶端電腦上重新整理群組原則後，您建立的新原則將不會生效。</span><span class="sxs-lookup"><span data-stu-id="175c5-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="175c5-214">雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：</span><span class="sxs-lookup"><span data-stu-id="175c5-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="175c5-215">您可以從任何以系統管理員認證執行的命令視窗中執行此命令。</span><span class="sxs-lookup"><span data-stu-id="175c5-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="175c5-216">若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。</span><span class="sxs-lookup"><span data-stu-id="175c5-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="175c5-217">請記住，這些原則應該針對您的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="175c5-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="175c5-218">它們不應用於執行商務用 Skype 伺服器的伺服器。</span><span class="sxs-lookup"><span data-stu-id="175c5-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="175c5-219">為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="175c5-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="175c5-220">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="175c5-221">在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="175c5-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="175c5-222">在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="175c5-223">以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。</span><span class="sxs-lookup"><span data-stu-id="175c5-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="175c5-224">在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="175c5-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="175c5-225">以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。</span><span class="sxs-lookup"><span data-stu-id="175c5-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="175c5-226">在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="175c5-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="175c5-227">按兩下 [ **不要使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="175c5-228">在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="175c5-229">關閉 [登錄編輯程式] 並 eboot 您的電腦。</span><span class="sxs-lookup"><span data-stu-id="175c5-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="175c5-230">在具有多個網路介面卡的電腦上設定服務品質</span><span class="sxs-lookup"><span data-stu-id="175c5-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="175c5-231">如果您的電腦有多個網路介面卡，您可能會在中執行某些問題： DSCP 值顯示為0x00，而不是設定的值。</span><span class="sxs-lookup"><span data-stu-id="175c5-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="175c5-232">這通常會發生在可能有一或多個網路介面卡無法存取您的 Active Directory 網域的電腦上 (例如，如果這些配接器是用於私人網路) 。</span><span class="sxs-lookup"><span data-stu-id="175c5-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="175c5-233">在此情況下，會針對可以存取網域的配接器標記 DSCP 值，但不會將其標記為無法存取網域的配接器。</span><span class="sxs-lookup"><span data-stu-id="175c5-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="175c5-234">如果您想要針對電腦中的所有網路介面卡標記 DSCP 值，包括沒有網域存取權的配接器，您必須在登錄中新增及設定值。</span><span class="sxs-lookup"><span data-stu-id="175c5-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="175c5-235">若要完成，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="175c5-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="175c5-236">按一下 **[開始]**，再按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="175c5-237">在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="175c5-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="175c5-238">在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="175c5-239">如果您看不到標示為 **QoS** 的登錄機碼，請以滑鼠右鍵按一下 [ **Tcpip**]，指向 [ **新增**]，然後按一下 [機 **碼**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="175c5-240">建立新的金鑰之後，輸入 **QoS**，然後按 enter 重新命名機碼。</span><span class="sxs-lookup"><span data-stu-id="175c5-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="175c5-241">以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。</span><span class="sxs-lookup"><span data-stu-id="175c5-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="175c5-242">在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。</span><span class="sxs-lookup"><span data-stu-id="175c5-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="175c5-243">按兩下 [ **不要使用 NLA**]。</span><span class="sxs-lookup"><span data-stu-id="175c5-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="175c5-244">在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="175c5-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="175c5-245">建立並設定新的登錄值後，您必須重新開機電腦，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="175c5-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="175c5-246">另請參閱</span><span class="sxs-lookup"><span data-stu-id="175c5-246">See also</span></span>

[<span data-ttu-id="175c5-247">在 Windows 10 中建立群組原則物件</span><span class="sxs-lookup"><span data-stu-id="175c5-247">Create a Group Policy Object in Windows 10</span></span>](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)