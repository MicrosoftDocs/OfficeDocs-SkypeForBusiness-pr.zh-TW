---
title: Lync Server 2013： 使用 cmdlet 反向樹系準備
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
ms.openlocfilehash: 4d39992255bfe6f93d9f41380b4f6b5fb9af1f5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="78139-102">使用 cmdlet 反向樹系準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78139-102">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78139-103">_**上次修改主題：** 2013年-06-19_</span><span class="sxs-lookup"><span data-stu-id="78139-103">_**Topic Last Modified:** 2013-06-19_</span></span>

<span data-ttu-id="78139-104">使用**Disable-csadforest** cmdlet 反向樹系準備步驟。</span><span class="sxs-lookup"><span data-stu-id="78139-104">Use the **Disable-CsAdForest** cmdlet to reverse the forest preparation step.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="78139-105">如果您執行<STRONG>Disable-csadforest</STRONG> cmdlet 也有舊版的環境中部署 Lync Server，舊版的全域設定也會一併刪除。</span><span class="sxs-lookup"><span data-stu-id="78139-105">If you run the <STRONG>Disable-CsAdForest</STRONG> cmdlet in an environment where you also have a previous version of Lync Server deployed, the global settings for the previous version will also be deleted.</span></span>



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a><span data-ttu-id="78139-106">若要使用 cmdlet 反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="78139-106">To use cmdlets to reverse forest preparation</span></span>

1.  <span data-ttu-id="78139-107">登入已加入網域的樹系根網域中 Domain Admins 群組成員身分的電腦。</span><span class="sxs-lookup"><span data-stu-id="78139-107">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="78139-108">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="78139-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="78139-109">執行：</span><span class="sxs-lookup"><span data-stu-id="78139-109">Run:</span></span>
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    <span data-ttu-id="78139-110">例如：</span><span class="sxs-lookup"><span data-stu-id="78139-110">For example:</span></span>
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    <span data-ttu-id="78139-111">Force 參數會指定是否強制執行工作。</span><span class="sxs-lookup"><span data-stu-id="78139-111">The Force parameter specifies whether to force running the task.</span></span> <span data-ttu-id="78139-112">如果這個參數不存在，如果針對 Lync Server 2013 仍然準備即使是一個樹系中的網域，將不會執行命令。</span><span class="sxs-lookup"><span data-stu-id="78139-112">If this parameter is not present, the command will not run if even one domain in the forest is still prepared for Lync Server 2013.</span></span> <span data-ttu-id="78139-113">如果指定 Force 參數，則巨集指令將繼續不論樹系中其他網域的狀態。</span><span class="sxs-lookup"><span data-stu-id="78139-113">If the Force parameter is specified, the action will continue regardless of the state of other domains in the forest.</span></span>
    
    <span data-ttu-id="78139-114">如果您未指定 GroupDomain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="78139-114">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78139-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78139-115">See Also</span></span>


[<span data-ttu-id="78139-116">執行 Lync Server 2013 的樹系準備</span><span class="sxs-lookup"><span data-stu-id="78139-116">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)  


[<span data-ttu-id="78139-117">準備樹系的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78139-117">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

