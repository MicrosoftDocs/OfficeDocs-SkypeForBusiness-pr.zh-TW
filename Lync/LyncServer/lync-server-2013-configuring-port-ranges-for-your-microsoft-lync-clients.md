---
title: Lync Server 2013：為您的 Microsoft Lync 用戶端配置埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="edae2-102">在 Lync Server 2013 中為您的 Microsoft Lync 用戶端設定埠範圍</span><span class="sxs-lookup"><span data-stu-id="edae2-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edae2-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="edae2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="edae2-104">根據預設，Lync 用戶端應用程式在通訊會話中參與時，可以使用埠1024和65535之間的任何埠;這是因為不會針對用戶端自動啟用特定的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="edae2-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="edae2-105">不過，若要使用服務品質，您需要將各種類型的流量（音訊、影片、媒體、應用程式共用及檔案傳輸）重新指派到一系列的唯一端口範圍。</span><span class="sxs-lookup"><span data-stu-id="edae2-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="edae2-106">您可以使用 CsConferencingConfiguration Cmdlet 來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="edae2-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edae2-107">最終使用者無法自行進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="edae2-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="edae2-108">只有系統管理員才能使用 CsConferencingConfiguration Cmdlet 進行埠變更。</span><span class="sxs-lookup"><span data-stu-id="edae2-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="edae2-109">您可以從 Microsoft Lync Server 2013 管理命令介面中執行下列命令，以判斷通訊會話目前使用的是哪個埠範圍：</span><span class="sxs-lookup"><span data-stu-id="edae2-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="edae2-110">假設您在安裝 Lync Server 2013 後沒有進行任何對會議設定所做的變更，您應該會返回包含這些屬性值的資訊：</span><span class="sxs-lookup"><span data-stu-id="edae2-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="edae2-111">如果您仔細查看上述輸出，您會看到兩個重要事項。</span><span class="sxs-lookup"><span data-stu-id="edae2-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="edae2-112">首先，ClientMediaPortRangeEnabled 屬性會設定為 False：</span><span class="sxs-lookup"><span data-stu-id="edae2-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="edae2-113">這個重要的是，因為當這個屬性設定為 False 時，Lync 用戶端會在通訊會話中參與時，使用埠1024和65535之間的任何可用埠;無論任何其他的埠設定（例如，ClientMediaPort 或 ClientVideoPort），都是如此。</span><span class="sxs-lookup"><span data-stu-id="edae2-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="edae2-114">如果您想要將使用量限制在指定的一組埠（如果您是在執行服務品質時進行規劃），您必須先啟用用戶端媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="edae2-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="edae2-115">可以使用下列 Windows PowerShell 命令完成：</span><span class="sxs-lookup"><span data-stu-id="edae2-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="edae2-116">上述命令可讓用戶端媒體埠範圍用於全域集合會議設定。不過，這些設定也可以套用至網站範圍和/或服務範圍（僅適用于會議服務器服務）。</span><span class="sxs-lookup"><span data-stu-id="edae2-116">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="edae2-117">若要啟用特定網站或伺服器的用戶端媒體埠範圍，請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的身分識別：</span><span class="sxs-lookup"><span data-stu-id="edae2-117">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="edae2-118">或者，您也可以使用此命令同時啟用所有會議設定的埠範圍：</span><span class="sxs-lookup"><span data-stu-id="edae2-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="edae2-119">您會注意到的第二個重要事項是，樣本輸出顯示針對每種類型的網路流量所設定的媒體埠範圍是完全相同的：</span><span class="sxs-lookup"><span data-stu-id="edae2-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="edae2-120">為了實現 QoS，這些埠範圍中的每一個都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="edae2-120">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="edae2-121">例如，您可以設定埠範圍，如下所示：</span><span class="sxs-lookup"><span data-stu-id="edae2-121">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="edae2-122">用戶端流量類型</span><span class="sxs-lookup"><span data-stu-id="edae2-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="edae2-123">埠開始</span><span class="sxs-lookup"><span data-stu-id="edae2-123">Port Start</span></span></th>
<th><span data-ttu-id="edae2-124">埠範圍</span><span class="sxs-lookup"><span data-stu-id="edae2-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="edae2-125">音訊</span><span class="sxs-lookup"><span data-stu-id="edae2-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="edae2-126">50020</span><span class="sxs-lookup"><span data-stu-id="edae2-126">50020</span></span></p></td>
<td><p><span data-ttu-id="edae2-127">20</span><span class="sxs-lookup"><span data-stu-id="edae2-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edae2-128">顯示器</span><span class="sxs-lookup"><span data-stu-id="edae2-128">Video</span></span></p></td>
<td><p><span data-ttu-id="edae2-129">58000</span><span class="sxs-lookup"><span data-stu-id="edae2-129">58000</span></span></p></td>
<td><p><span data-ttu-id="edae2-130">20</span><span class="sxs-lookup"><span data-stu-id="edae2-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="edae2-131">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="edae2-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="edae2-132">42000</span><span class="sxs-lookup"><span data-stu-id="edae2-132">42000</span></span></p></td>
<td><p><span data-ttu-id="edae2-133">20</span><span class="sxs-lookup"><span data-stu-id="edae2-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="edae2-134">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="edae2-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="edae2-135">42020</span><span class="sxs-lookup"><span data-stu-id="edae2-135">42020</span></span></p></td>
<td><p><span data-ttu-id="edae2-136">20</span><span class="sxs-lookup"><span data-stu-id="edae2-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="edae2-137">在前一個表格中，用戶端埠範圍代表伺服器設定的埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="edae2-137">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="edae2-138">例如，在伺服器上，應用程式共用已設定為使用埠40803到 49151;在用戶端電腦上，應用程式共用設定為使用埠42000到42019。</span><span class="sxs-lookup"><span data-stu-id="edae2-138">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="edae2-139">如此一來，也主要是為了簡化 QoS 的管理：用戶端埠不需要代表伺服器上所用埠的子集。</span><span class="sxs-lookup"><span data-stu-id="edae2-139">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="edae2-140">（例如，您可以在用戶端電腦上設定要使用的應用程式共用，比如說埠10000到10019。）不過，建議您將用戶端埠範圍設為伺服器埠範圍的子集。</span><span class="sxs-lookup"><span data-stu-id="edae2-140">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="edae2-141">此外，您可能已經注意到8348埠已針對伺服器上的應用程式共用而設定，但用戶端上的應用程式共用只留有20個埠。</span><span class="sxs-lookup"><span data-stu-id="edae2-141">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="edae2-142">我們也建議您這麼做，但不是很難且快速的規則。</span><span class="sxs-lookup"><span data-stu-id="edae2-142">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="edae2-143">一般來說，您可以考慮每個可用的埠代表單一通訊會話：如果埠範圍中有可用的100埠，表示有問題的電腦在任何特定時間都可以參與（最多100通訊會話）。</span><span class="sxs-lookup"><span data-stu-id="edae2-143">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="edae2-144">因為伺服器可能會參與許多用戶端的交談，所以在伺服器上開啟的埠數會比用戶端多。</span><span class="sxs-lookup"><span data-stu-id="edae2-144">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="edae2-145">為用戶端上的應用程式共用設定20個埠，意味著使用者可以同時在指定的裝置上參與20個應用程式共用會話。</span><span class="sxs-lookup"><span data-stu-id="edae2-145">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="edae2-146">這對於絕大多數使用者而言，都應該有足夠的證明。</span><span class="sxs-lookup"><span data-stu-id="edae2-146">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="edae2-147">若要將先前的埠範圍指派給您的全域會議設定設定，您可以使用下列 Lync Server Management Shell 命令：</span><span class="sxs-lookup"><span data-stu-id="edae2-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="edae2-148">或者，您可以使用這個命令，為所有的會議設定指派相同的埠範圍：</span><span class="sxs-lookup"><span data-stu-id="edae2-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="edae2-149">個別使用者必須從 Lync 登出，然後重新登入，這些變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="edae2-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edae2-150">您也可以使用單一命令來啟用用戶端媒體埠範圍，然後指派這些埠範圍。</span><span class="sxs-lookup"><span data-stu-id="edae2-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="edae2-151">例如：</span><span class="sxs-lookup"><span data-stu-id="edae2-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

