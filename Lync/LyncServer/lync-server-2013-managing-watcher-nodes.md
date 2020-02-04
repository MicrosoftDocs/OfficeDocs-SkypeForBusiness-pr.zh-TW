---
title: Lync Server 2013：管理觀察程式節點
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
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="b44b6-102">在 Lync Server 2013 中管理觀察程式節點</span><span class="sxs-lookup"><span data-stu-id="b44b6-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b44b6-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b44b6-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b44b6-104">除了修改在觀察程式節點上執行的綜合交易之外，系統管理員還可以使用**CsWatcherNodeConfiguration** Cmdlet 來執行兩個其他重要的工作：啟用和停用觀察程式節點，以及將觀察程式節點設定為在執行測試時使用內部 url 或外部 url。</span><span class="sxs-lookup"><span data-stu-id="b44b6-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="b44b6-105">根據預設，觀察程式節點是設計來定期執行所有已啟用的綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b44b6-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="b44b6-106">不過，有時候您可能需要暫停這些交易。</span><span class="sxs-lookup"><span data-stu-id="b44b6-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="b44b6-107">例如，如果 [觀察程式] 節點暫時與網路中斷連線，則沒有任何理由執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b44b6-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="b44b6-108">若沒有網路連線，這些事務就會保證失敗。</span><span class="sxs-lookup"><span data-stu-id="b44b6-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="b44b6-109">如果您想要暫時停用 [觀察程式] 節點，請從 Lync Server 管理命令介面執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="b44b6-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="b44b6-110">這個命令將停用在觀察程式節點上執行的綜合交易（atl-觀察程式-001.litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="b44b6-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="b44b6-111">若要繼續執行綜合交易，請將 Enabled 屬性設回 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="b44b6-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="b44b6-112">可使用 Enabled 屬性來開啟或關閉觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="b44b6-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="b44b6-113">如果您想要永久刪除 [觀察程式] 節點，請使用<STRONG>CsWatcherNodeConfiguration</STRONG> Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b44b6-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="b44b6-114">移除-CsWatcherNodeConfiguration –身分識別 "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="b44b6-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="b44b6-115">該命令會從指定的電腦中移除所有的觀察程式節點設定，這可防止電腦自動執行綜合交易。</span><span class="sxs-lookup"><span data-stu-id="b44b6-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="b44b6-116">不過，命令不會卸載 System Center 代理程式檔案或 Lync Server 2013 系統檔案。</span><span class="sxs-lookup"><span data-stu-id="b44b6-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="b44b6-117">根據預設，觀察程式節點會在進行測試時使用組織的外部 Url。</span><span class="sxs-lookup"><span data-stu-id="b44b6-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="b44b6-118">不過，您也可以將觀察程式節點設定為使用組織的內部 Url。</span><span class="sxs-lookup"><span data-stu-id="b44b6-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="b44b6-119">這可讓系統管理員驗證位於周邊網路內之使用者的 URL 存取權。</span><span class="sxs-lookup"><span data-stu-id="b44b6-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="b44b6-120">若要將觀察程式節點設定為使用內部 Url，而不是外部 Url，請將 UseInternalWebUrls 屬性設為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="b44b6-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="b44b6-121">如果您將這個屬性重設為預設值 False （$False），則觀察程式就會使用外部 Url：</span><span class="sxs-lookup"><span data-stu-id="b44b6-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

