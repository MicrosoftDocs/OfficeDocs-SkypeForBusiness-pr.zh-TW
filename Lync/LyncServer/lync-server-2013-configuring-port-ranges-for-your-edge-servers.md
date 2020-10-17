---
title: Lync Server 2013：設定 Edge server 的埠範圍
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
ms.openlocfilehash: a9124ba5b2a800190f49a9ac81fd9a2477eac215
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535020"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="723be-102">在 Lync Server 2013 中設定 Edge server 的埠範圍</span><span class="sxs-lookup"><span data-stu-id="723be-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="723be-103">_**主題上次修改日期：** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="723be-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="723be-104">有了 Edge 伺服器，您不需要針對音訊、視訊與應用程式共用設定個別連接埠範圍；同樣地，用於 Edge 伺服器的連接埠範圍也無須符合與您會議伺服器、應用程式伺服器以及中繼伺服器搭配使用的連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="723be-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="723be-105">在繼續進行我們的範例之前，請務必強調此選項存在時，我們建議您不要變更埠範圍，因為當您移出50000埠範圍時，可能會對某些案例產生負面影響。</span><span class="sxs-lookup"><span data-stu-id="723be-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="723be-106">例如，假設您已設定會議、應用程式以及中繼伺服器以使用這些連接埠範圍：</span><span class="sxs-lookup"><span data-stu-id="723be-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="723be-107">封包類型</span><span class="sxs-lookup"><span data-stu-id="723be-107">Packet Type</span></span></th>
<th><span data-ttu-id="723be-108">起始連接埠</span><span class="sxs-lookup"><span data-stu-id="723be-108">Starting Port</span></span></th>
<th><span data-ttu-id="723be-109">已保留連接埠數目</span><span class="sxs-lookup"><span data-stu-id="723be-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="723be-110">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="723be-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="723be-111">40803</span><span class="sxs-lookup"><span data-stu-id="723be-111">40803</span></span></p></td>
<td><p><span data-ttu-id="723be-112">8348</span><span class="sxs-lookup"><span data-stu-id="723be-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="723be-113">音訊</span><span class="sxs-lookup"><span data-stu-id="723be-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="723be-114">49152</span><span class="sxs-lookup"><span data-stu-id="723be-114">49152</span></span></p></td>
<td><p><span data-ttu-id="723be-115">8348</span><span class="sxs-lookup"><span data-stu-id="723be-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="723be-116">影片</span><span class="sxs-lookup"><span data-stu-id="723be-116">Video</span></span></p></td>
<td><p><span data-ttu-id="723be-117">57500</span><span class="sxs-lookup"><span data-stu-id="723be-117">57500</span></span></p></td>
<td><p><span data-ttu-id="723be-118">8034</span><span class="sxs-lookup"><span data-stu-id="723be-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="723be-119"><strong>總數</strong></span><span class="sxs-lookup"><span data-stu-id="723be-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="723be-120">24730</span><span class="sxs-lookup"><span data-stu-id="723be-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="723be-121">如您所見，音訊、影片和應用程式共用的埠範圍會從埠40803開始，並包含24732埠的總數。</span><span class="sxs-lookup"><span data-stu-id="723be-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="723be-122">您可依喜好設定某個 Edge Server，透過執行類似下列 Lync Server Management Shell 命令以使用這些全部的連接埠值：</span><span class="sxs-lookup"><span data-stu-id="723be-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="723be-123">或者，使用下列命令以在組織中同時設定所有 Edge 伺服器：</span><span class="sxs-lookup"><span data-stu-id="723be-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="723be-124">您可以使用下列 Lync Server 管理命令介面命令來驗證 Edge server 的目前埠設定：</span><span class="sxs-lookup"><span data-stu-id="723be-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="723be-125">同樣地，我們確實提供這些選項，我們強烈建議您保留其為埠設定的內容。</span><span class="sxs-lookup"><span data-stu-id="723be-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

