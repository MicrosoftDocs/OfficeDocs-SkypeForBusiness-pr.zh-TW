---
title: Lync Server 2013：匯出和匯入語音路由組態
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
ms.openlocfilehash: 23ca3642204e4097f5345f879c704dcfcb4d8c9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="3a16e-102">在 Lync Server 2013 中匯出和匯入語音路由組態</span><span class="sxs-lookup"><span data-stu-id="3a16e-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a16e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3a16e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3a16e-104">如果您想要儲存語音路由設定，但不發佈它，請依照下列步驟使用 Lync Server [控制台] 的 [匯出及匯入] 命令來儲存及取得語音路由設定的快照。</span><span class="sxs-lookup"><span data-stu-id="3a16e-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="3a16e-105">當您匯入語音路由設定檔（vcfg），但同時又在伺服器上對語音路由設定進行變更時，Lync Server [控制台] 中的 [**語音路由**] 群組中的頁面將會顯示 [語音路由] 中有未提交的變更。</span><span class="sxs-lookup"><span data-stu-id="3a16e-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="3a16e-106">那些未提交的變更是兩個需要調解的設定之間的差異。</span><span class="sxs-lookup"><span data-stu-id="3a16e-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3a16e-107">如果您已對 [<STRONG>語音路由</STRONG>] 群組內任何頁面上的設定進行任何未提交的變更，這些變更會儲存在匯出的語音設定檔案（vcfg）中。</span><span class="sxs-lookup"><span data-stu-id="3a16e-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="3a16e-108">這可讓您在發佈變更前，在多個 Lync Server 控制台會話期間進行語音路由設定變更。</span><span class="sxs-lookup"><span data-stu-id="3a16e-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3a16e-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="3a16e-109">In This Section</span></span>

  - [<span data-ttu-id="3a16e-110">在 Lync Server 2013 中匯出語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="3a16e-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="3a16e-111">在 Lync Server 2013 中匯入語音路由組態檔</span><span class="sxs-lookup"><span data-stu-id="3a16e-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3a16e-112">相關各節</span><span class="sxs-lookup"><span data-stu-id="3a16e-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

