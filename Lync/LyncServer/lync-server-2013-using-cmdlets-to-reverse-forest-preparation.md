---
title: Lync Server 2013：使用 Cmdlet 進行反向樹系準備
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
ms.openlocfilehash: 2e3104f07934e590dc22ac9f5000601bc8166b6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535790"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="2381a-102">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="2381a-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2381a-103">_**主題上次修改日期：** 2013-06-19_</span><span class="sxs-lookup"><span data-stu-id="2381a-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="2381a-104">使用 **Disable-CsAdForest** Cmdlet 來反向樹系準備步驟。</span><span class="sxs-lookup"><span data-stu-id="2381a-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2381a-105">如果您在也部署舊版 Lync Server 的環境中執行 <STRONG>Disable-CsAdForest</STRONG> 指令程式，則舊版本的通用設定也會被刪除。</span><span class="sxs-lookup"><span data-stu-id="2381a-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="2381a-106">若要使用 Cmdlet 進行反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="2381a-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="2381a-107">以樹系根域的 Domain Admins 群組成員身分登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="2381a-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="2381a-108">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="2381a-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2381a-109">運行：</span><span class="sxs-lookup"><span data-stu-id="2381a-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="2381a-110">例如：</span><span class="sxs-lookup"><span data-stu-id="2381a-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="2381a-111">Force 參數會指定是否強制執行任務。</span><span class="sxs-lookup"><span data-stu-id="2381a-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="2381a-112">如果此參數不存在，則即使樹系中的一個網域仍為 Lync Server 2013 做好準備，此命令也不會執行。</span><span class="sxs-lookup"><span data-stu-id="2381a-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="2381a-113">如果指定 Force 參數，不論樹系中其他網域的狀態為何，該動作都會繼續。</span><span class="sxs-lookup"><span data-stu-id="2381a-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="2381a-114">如果您未指定 GroupDomain 參數，則預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="2381a-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2381a-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2381a-115">See Also</span></span>


[<span data-ttu-id="2381a-116">對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="2381a-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="2381a-117">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="2381a-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

