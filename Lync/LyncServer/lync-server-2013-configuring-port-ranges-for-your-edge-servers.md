---
title: Lync Server 2013： 設定您的 Edge Server 的連接埠範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1d1dc6c35cac0a375b9229a0a9e04664bfe868a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="015d5-102">設定 Lync Server 2013 Edge Server 的連接埠範圍</span><span class="sxs-lookup"><span data-stu-id="015d5-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="015d5-103">_**主題上次修改日期：** 2015年-07-24_</span><span class="sxs-lookup"><span data-stu-id="015d5-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="015d5-104">有了 Edge 伺服器，您不需要針對音訊、視訊與應用程式共用設定個別連接埠範圍；同樣地，用於 Edge 伺服器的連接埠範圍也無須符合與您會議伺服器、應用程式伺服器以及中繼伺服器搭配使用的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="015d5-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="015d5-105">我們繼續使用我們的範例之前，請務必壓力，雖然這個選項存在，我們建議您不要變更的連接埠範圍，因為如果您移動超過 50000 的連接埠範圍，這可能會造成負面影響某些情況。</span><span class="sxs-lookup"><span data-stu-id="015d5-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="015d5-106">例如，假設您已設定會議、應用程式以及中繼伺服器以使用這些連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="015d5-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="015d5-107">封包類型</span><span class="sxs-lookup"><span data-stu-id="015d5-107">Packet Type</span></span></th>
<th><span data-ttu-id="015d5-108">起始連接埠</span><span class="sxs-lookup"><span data-stu-id="015d5-108">Starting Port</span></span></th>
<th><span data-ttu-id="015d5-109">已保留連接埠數目</span><span class="sxs-lookup"><span data-stu-id="015d5-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="015d5-110">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="015d5-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="015d5-111">40803</span><span class="sxs-lookup"><span data-stu-id="015d5-111">40803</span></span></p></td>
<td><p><span data-ttu-id="015d5-112">8348</span><span class="sxs-lookup"><span data-stu-id="015d5-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="015d5-113">音訊</span><span class="sxs-lookup"><span data-stu-id="015d5-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="015d5-114">49152</span><span class="sxs-lookup"><span data-stu-id="015d5-114">49152</span></span></p></td>
<td><p><span data-ttu-id="015d5-115">8348</span><span class="sxs-lookup"><span data-stu-id="015d5-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="015d5-116">影片</span><span class="sxs-lookup"><span data-stu-id="015d5-116">Video</span></span></p></td>
<td><p><span data-ttu-id="015d5-117">57500</span><span class="sxs-lookup"><span data-stu-id="015d5-117">57500</span></span></p></td>
<td><p><span data-ttu-id="015d5-118">8034</span><span class="sxs-lookup"><span data-stu-id="015d5-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="015d5-119"><strong>總計</strong></span><span class="sxs-lookup"><span data-stu-id="015d5-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="015d5-120">24730</span><span class="sxs-lookup"><span data-stu-id="015d5-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="015d5-121">如您所見，您的連接埠範圍的音訊、 視訊及應用程式共用連接埠 40803 開始，並包含 24732 連接埠總數。</span><span class="sxs-lookup"><span data-stu-id="015d5-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="015d5-122">您可依喜好設定某個 Edge Server，透過執行類似下列 Lync Server Management Shell 命令以使用這些全部的連接埠值：</span><span class="sxs-lookup"><span data-stu-id="015d5-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="015d5-123">或者，使用下列命令以在組織中同時設定所有 Edge 伺服器：</span><span class="sxs-lookup"><span data-stu-id="015d5-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="015d5-124">您可以使用此 Lync Server 管理命令介面命令，以確認 Edge 伺服器目前的連接埠設定：</span><span class="sxs-lookup"><span data-stu-id="015d5-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="015d5-125">同樣地，我們提供這些選項，雖然我們強烈建議您將保留事項，因為它們是連接埠設定。</span><span class="sxs-lookup"><span data-stu-id="015d5-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

