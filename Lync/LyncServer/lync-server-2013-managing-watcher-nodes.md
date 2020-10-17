---
title: Lync Server 2013：管理觀察程式節點
description: Lync Server 2013：管理觀察程式節點。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556609"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="e2f51-103">在 Lync Server 2013 中管理觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="e2f51-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2f51-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e2f51-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e2f51-105">除了修改在監看員節點上執行的綜合交易之外，系統管理員也可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來執行其他兩項重要工作：啟用與停用監看員節點，以及設定監看員節點於執行測試時使用內部 URL 或外部 URL。</span><span class="sxs-lookup"><span data-stu-id="e2f51-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="e2f51-106">根據預設，監看員節點的設計是會定時執行所有啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="e2f51-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="e2f51-107">不過有時候可能需要暫停那些交易。</span><span class="sxs-lookup"><span data-stu-id="e2f51-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="e2f51-108">例如，如果監看員節點暫時與網路中斷連線，則沒有必要執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="e2f51-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="e2f51-109">沒有網路連線，那些交易一定會失敗。</span><span class="sxs-lookup"><span data-stu-id="e2f51-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="e2f51-110">如果您想要暫時停用監看員節點，請從 Lync Server 管理命令介面執行類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="e2f51-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="e2f51-p102">此命令會停用監看員節點 atl-watcher- 001.litwareinc.com 上的綜合交易執行。若要恢復綜合交易的執行，請將 Enabled 屬性回復至 True ($True) 設定：</span><span class="sxs-lookup"><span data-stu-id="e2f51-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="e2f51-113">Enabled 屬性可用於開啟或關閉監看員節點。</span><span class="sxs-lookup"><span data-stu-id="e2f51-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="e2f51-114">如果要永久刪除監看員節點，請使用 <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e2f51-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="e2f51-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="e2f51-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="e2f51-116">此命令會移除指定電腦上所有的監看員節點組態設定，這樣就會防止電腦自動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="e2f51-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="e2f51-117">不過，此命令不會卸載 System Center 代理檔或 Lync Server 2013 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="e2f51-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="e2f51-p105">根據預設，監看員節點在進行測試時，會使用組織的外部 URL。不過也可以設定監看員節點使用組織的內部 URL。這讓系統管理員可以驗證位於周邊網路內之使用者的 URL 存取。若要設定監看員節點使用內部 URL 而非外部 URL，請將 UseInternalWebUrls 屬性設為 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="e2f51-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="e2f51-122">如果重設此屬性為預設值 False ($False)，監看員就會使用外部 URL：</span><span class="sxs-lookup"><span data-stu-id="e2f51-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

