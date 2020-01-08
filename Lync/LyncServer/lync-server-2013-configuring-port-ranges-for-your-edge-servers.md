---
title: Lync Server 2013：為邊緣伺服器設定埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73827b9c16903a6b3cf06f0c56446c0409fb9cd4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3733d-102">在 Lync Server 2013 中設定邊緣伺服器的埠範圍</span><span class="sxs-lookup"><span data-stu-id="3733d-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3733d-103">_**主題上次修改日期：** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="3733d-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="3733d-104">有了 Edge 伺服器，您就不需要為音訊、影片和應用程式共用設定個別的埠範圍;同樣地，邊緣伺服器所用的埠範圍不一定要與您的會議、應用程式及中繼伺服器所使用的埠範圍相符。</span><span class="sxs-lookup"><span data-stu-id="3733d-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="3733d-105">在繼續進行我們的範例之前，請務必先將這個選項提供給您，但我們建議您不要變更埠範圍，因為如果您移出50000埠範圍，就可能會對某些案例造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="3733d-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="3733d-106">例如，假設您已將會議、應用程式和中繼伺服器設定為使用這些埠範圍：</span><span class="sxs-lookup"><span data-stu-id="3733d-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3733d-107">資料包類型</span><span class="sxs-lookup"><span data-stu-id="3733d-107">Packet Type</span></span></th>
<th><span data-ttu-id="3733d-108">起始埠</span><span class="sxs-lookup"><span data-stu-id="3733d-108">Starting Port</span></span></th>
<th><span data-ttu-id="3733d-109">保留的埠數</span><span class="sxs-lookup"><span data-stu-id="3733d-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3733d-110">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="3733d-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="3733d-111">40803</span><span class="sxs-lookup"><span data-stu-id="3733d-111">40803</span></span></p></td>
<td><p><span data-ttu-id="3733d-112">8348</span><span class="sxs-lookup"><span data-stu-id="3733d-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3733d-113">音訊</span><span class="sxs-lookup"><span data-stu-id="3733d-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="3733d-114">49152</span><span class="sxs-lookup"><span data-stu-id="3733d-114">49152</span></span></p></td>
<td><p><span data-ttu-id="3733d-115">8348</span><span class="sxs-lookup"><span data-stu-id="3733d-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3733d-116">顯示器</span><span class="sxs-lookup"><span data-stu-id="3733d-116">Video</span></span></p></td>
<td><p><span data-ttu-id="3733d-117">57500</span><span class="sxs-lookup"><span data-stu-id="3733d-117">57500</span></span></p></td>
<td><p><span data-ttu-id="3733d-118">8034</span><span class="sxs-lookup"><span data-stu-id="3733d-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3733d-119"><strong>本壘</strong></span><span class="sxs-lookup"><span data-stu-id="3733d-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="3733d-120">24730</span><span class="sxs-lookup"><span data-stu-id="3733d-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3733d-121">如您所見，音訊、影片和應用程式共用的埠範圍是從埠40803開始，並包含總共24732個埠。</span><span class="sxs-lookup"><span data-stu-id="3733d-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="3733d-122">如果您想要的話，您可以將指定的邊緣伺服器設定成在 Lync Server 管理命令介面中執行如下的命令，以使用這些整體埠值：</span><span class="sxs-lookup"><span data-stu-id="3733d-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="3733d-123">或者，使用下列命令同時設定貴組織中的所有邊緣伺服器：</span><span class="sxs-lookup"><span data-stu-id="3733d-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="3733d-124">您可以使用此 Lync Server Management Shell 命令來驗證 Edge 伺服器的目前埠設定：</span><span class="sxs-lookup"><span data-stu-id="3733d-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="3733d-125">同樣地，雖然我們確實提供這些選項，但我們強烈建議您將它們留給埠配置。</span><span class="sxs-lookup"><span data-stu-id="3733d-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

