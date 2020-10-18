---
title: Lync Server 2013：使用 Cmdlet 進行反向樹系準備
description: Lync Server 2013：使用 Cmdlet 進行反向樹系準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580389"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="b1ae8-103">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="b1ae8-103">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1ae8-104">_**主題上次修改日期：** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="b1ae8-104">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="b1ae8-105">使用 **Disable-CsAdForest** Cmdlet 來反向樹系準備步驟。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-105">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b1ae8-106">如果您在也部署舊版 Lync Server 的環境中執行 <STRONG>Disable-CsAdForest</STRONG> 指令程式，則舊版本的通用設定也會被刪除。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-106">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="b1ae8-107">若要使用 Cmdlet 進行反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="b1ae8-107">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="b1ae8-108">以樹系根域的 Domain Admins 群組成員身分登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-108">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="b1ae8-109">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b1ae8-110">運行：</span><span class="sxs-lookup"><span data-stu-id="b1ae8-110">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="b1ae8-111">例如：</span><span class="sxs-lookup"><span data-stu-id="b1ae8-111">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="b1ae8-112">Force 參數會指定是否強制執行任務。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-112">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="b1ae8-113">如果此參數不存在，則即使樹系中的一個網域仍為 Lync Server 2013 做好準備，此命令也不會執行。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-113">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="b1ae8-114">如果指定 Force 參數，不論樹系中其他網域的狀態為何，該動作都會繼續。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-114">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="b1ae8-115">如果您未指定 GroupDomain 參數，則預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="b1ae8-115">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1ae8-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1ae8-116">See Also</span></span>


[<span data-ttu-id="b1ae8-117">對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="b1ae8-117">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="b1ae8-118">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="b1ae8-118">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

