---
title: Lync Server 2013：拓撲測試發生問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7095e539ec8e9cc832b4ce69f2e347bfcea38ccc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514030"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="b1c1c-102">Lync Server 2013 中的拓撲測試問題</span><span class="sxs-lookup"><span data-stu-id="b1c1c-102">Issues with the topology test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1c1c-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b1c1c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b1c1c-104">就像 **Test-CsTopology** Cmdlet 一樣，最佳做法 Analyzer 為您提供一種方法，讓您能夠驗證 Lync Server 2013 在全域層級是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="b1c1c-105">根據預設，最佳做法分析器（如 Cmdlet）會檢查整個 Lync Server 2013 基礎結構、驗證所需的服務是否在執行中，以及已針對您安裝 Lync Server 2013 時所建立的通用安全性群組，設定適當的使用者權限與許可權。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="b1c1c-106">除了驗證 Lync Server 的有效性， **Test-CsTopology** 也會檢查特定服務的有效性。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="b1c1c-107">如需使用 Cmdlet 來測試特定服務的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="b1c1c-108">使用下列資訊有助於解決您拓撲的問題。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1c1c-p103">端視 Edge Server 以及任何相關周邊網路設定而定，包括防火牆設定和周邊，Best Practices Analyzer 可能無法存取和掃描 Edge Server。如果將 Edge Server 包含在掃描內，而且報告指出存取 Edge Server 發生問題，請清除 [Edge Server]<STRONG></STRONG> 核取方塊，並再次執行掃描，以避免問題出現在報告中。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="b1c1c-111">解決拓撲的問題</span><span class="sxs-lookup"><span data-stu-id="b1c1c-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="b1c1c-112">如果拓撲測試發現拓撲的問題，這些問題可能是在您發行或啟用拓撲時發生的問題所造成。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="b1c1c-113">變更拓撲時，變更在發行和啟用後才會生效。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="b1c1c-114">您必須使用拓撲產生器，才能變更拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="b1c1c-115">進行變更之後，您可以使用拓撲產生器來發佈及啟用這些變更。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="b1c1c-116">當您發佈變更時，新的資訊 (例如，新的網站或新的伺服器角色) 會寫入中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="b1c1c-117">不過，這些新物件 (或新修改的物件) 並不會立即加入您的拓撲中。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="b1c1c-118">物件必須等到更新後的拓撲啟用後才會加入拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="b1c1c-119">如果您選取 [拓撲產生器] 中的 [發佈] 選項，則會進行下列兩個步驟：發佈變更 (也就是說，它們會寫入中央管理存放區) ，然後啟用新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="b1c1c-120">根據預設，RTCUniversalServerAdmins 群組的成員有權執行 **Publish-CsTopology** Cmdlet 和 **Enable-CsTopology** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="b1c1c-121">不過，如果尚未委派設定許可權，您必須以網域管理員身分登入，才能執行 **Publish-CsTopology**。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="b1c1c-122">若要讓 RTCUniversalServerAdmins 能夠實際使用 **Publish-CsTopology** 指令程式，您必須在包含執行 Lync Server 服務之電腦的每個 Active Directory 容器上執行 **Grant-CsSetupPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="b1c1c-123">若要讓 RTCUniversalServerAdmins 使用 **Enable-CsTopology** Cmdlet 的權利，您必須針對包含執行 Lync Server 服務之電腦的每個 Active Directory 網域服務容器執行 **test-cssetuppermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="b1c1c-124">請注意，這適用于使用拓撲產生器來啟用及發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="b1c1c-125">如果您未使用 **test-cssetuppermission**委派許可權，則只有網域管理員可以透過拓撲產生器來啟用及發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1c1c-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

