---
title: Lync Server 2013：匯出和匯入語音路由設定
description: Lync Server 2013：匯出和匯入語音路由設定。
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
ms.openlocfilehash: a94a9c02672debae9f5b30e3a1a96856050d6ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564769"
---
# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="950da-103">在 Lync Server 2013 中匯出及匯入語音路由設定</span><span class="sxs-lookup"><span data-stu-id="950da-103">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="950da-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="950da-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="950da-105">如果您想要儲存語音路由設定，但未發佈它，請遵循下列步驟，使用 Lync Server 控制台的 [匯出] 和 [匯入] 命令，儲存並取得您的語音路由設定快照。</span><span class="sxs-lookup"><span data-stu-id="950da-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="950da-106">當您匯入語音路由設定檔 (。 vcfg) ，但目前在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [ **語音** 路由] 群組中的頁面會指出有未認可的變更可供語音路由使用。</span><span class="sxs-lookup"><span data-stu-id="950da-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="950da-107">這些未認可的變更會使兩個設定出現差異且需要重新調整。</span><span class="sxs-lookup"><span data-stu-id="950da-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="950da-108">如果您已對 <STRONG>語音路由</STRONG> 群組內任何頁面上的設定進行任何未認可的變更，則所做的變更會儲存在匯出的語音設定檔中 (。 vcfg) 。</span><span class="sxs-lookup"><span data-stu-id="950da-108">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="950da-109">這可讓您在發佈變更之前，在多部 Lync Server 控制台會話期間進行語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="950da-109">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="950da-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="950da-110">In This Section</span></span>

  - [<span data-ttu-id="950da-111">在 Lync Server 2013 中匯出語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="950da-111">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="950da-112">在 Lync Server 2013 中匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="950da-112">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="950da-113">相關各節</span><span class="sxs-lookup"><span data-stu-id="950da-113">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

