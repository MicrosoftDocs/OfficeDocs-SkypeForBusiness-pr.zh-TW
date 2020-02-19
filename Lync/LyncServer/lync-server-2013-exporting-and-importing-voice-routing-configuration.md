---
title: Lync Server 2013： 匯出和匯入語音路由設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad2d37ee1768388e1cf246a7495f551380a3363
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="0a780-102">匯出及匯入 Lync Server 2013 中的語音路由設定</span><span class="sxs-lookup"><span data-stu-id="0a780-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a780-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a780-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a780-104">如果您想要儲存語音路由組態，而不發佈，請遵循下列步驟以使用 Lync Server Control Panel 組態匯出及匯入儲存和擷取的語音路由設定快照集的命令。</span><span class="sxs-lookup"><span data-stu-id="0a780-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="0a780-105">當您匯入語音路由組態檔 (.vcfg)，但語音路由組態的伺服器上同時進行變更時，Lync Server 控制台的 [**語音路由**] 群組中的頁面會指出有未認可的變更語音路由。</span><span class="sxs-lookup"><span data-stu-id="0a780-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="0a780-106">這些未認可的變更會使兩個設定出現差異且需要重新調整。</span><span class="sxs-lookup"><span data-stu-id="0a780-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0a780-107">如果您已在任何頁面上，[<STRONG>語音路由</STRONG>] 群組中的設定進行任何未認可的變更，會在匯出的語音組態檔 (.vcfg) 中儲存的變更。</span><span class="sxs-lookup"><span data-stu-id="0a780-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="0a780-108">這可讓您進行語音路由組態變更期間多個 Lync Server Control Panel 工作階段之前發佈的變更。</span><span class="sxs-lookup"><span data-stu-id="0a780-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a780-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0a780-109">In This Section</span></span>

  - [<span data-ttu-id="0a780-110">匯出在 Lync Server 2013 中的語音路由組態檔</span><span class="sxs-lookup"><span data-stu-id="0a780-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="0a780-111">匯入 Lync Server 2013 中的語音路由組態檔</span><span class="sxs-lookup"><span data-stu-id="0a780-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="0a780-112">相關各節</span><span class="sxs-lookup"><span data-stu-id="0a780-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

