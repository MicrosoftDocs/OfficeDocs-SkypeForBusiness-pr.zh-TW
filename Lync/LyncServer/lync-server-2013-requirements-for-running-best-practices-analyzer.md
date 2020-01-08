---
title: Lync Server 2013：執行最佳做法分析程式的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements for running Best Practices Analyzer
ms:assetid: 3c7dc44e-5f8a-40a7-9ebb-9ad707ac0007
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591345(v=OCS.15)
ms:contentKeyID: 48183880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdba078f60a4e2012840aedf618b2786181a47b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-running-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="f21c7-102">在 Lync Server 2013 中執行最佳做法分析程式的需求</span><span class="sxs-lookup"><span data-stu-id="f21c7-102">Requirements for running Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f21c7-103">_**主題上次修改日期：** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="f21c7-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="f21c7-104">您可以使用 Lync Server 2013、最佳做法分析程式來掃描您的 Lync Server 2013 環境。</span><span class="sxs-lookup"><span data-stu-id="f21c7-104">You can use Lync Server 2013, Best Practices Analyzer to scan your Lync Server 2013 environment.</span></span> <span data-ttu-id="f21c7-105">您無法使用它來掃描先前的環境，但是您可以使用舊版的工具來掃描這些環境。</span><span class="sxs-lookup"><span data-stu-id="f21c7-105">You cannot use it to scan previous environments, but you can use the previous versions of the tool to scan those environments.</span></span> <span data-ttu-id="f21c7-106">如需有關下載並使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 版最佳做法分析程式的詳細資料，請參閱「Lync Server 2010、最佳做法[http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358)分析程式」和「Office 通訊伺服器2007與 Office 通訊伺服器 2007 R2 的最佳做法[http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651)分析程式」。</span><span class="sxs-lookup"><span data-stu-id="f21c7-106">For details about downloading and using the Lync Server 2010 and Office Communications Server 2007 R2 versions of Best Practices Analyzer, see "Lync Server 2010, Best Practices Analyzer" at [http://go.microsoft.com/fwlink/p/?linkId=210536](http://go.microsoft.com/fwlink/p/?linkid=256358) and "Best Practices Analyzer for Office Communications Server 2007 and Office Communications Server 2007 R2" at [http://go.microsoft.com/fwlink/p/?linkId=256358](http://go.microsoft.com/fwlink/p/?linkid=210651).</span></span>

<span data-ttu-id="f21c7-107">開始進行掃描之前，您應該先確定 Lync Server 2013 環境中的所有元件都在執行和連線。</span><span class="sxs-lookup"><span data-stu-id="f21c7-107">Prior to starting your scan, you should ensure that all components in your Lync Server 2013 environment are running and online.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f21c7-108">根據 Edge 伺服器的設定以及任何相關的周邊網路設定（包括防火牆設定和許可權），最佳做法分析程式可能無法存取及掃描您的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="f21c7-108">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="f21c7-109">如果您在掃描中包含 Edge 伺服器，且報告指出存取邊緣伺服器時發生問題，您可能會想要從掃描選項中移除邊緣伺服器，然後再次執行掃描，以使問題不會顯示在報表中。</span><span class="sxs-lookup"><span data-stu-id="f21c7-109">If you include Edge Servers in your scan and the reports indicate that there is an issue with accessing Edge Servers, you might want to remove Edge Servers from the scan options and run the scan again so that the issues do not show up in the report.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

