---
title: Lync Server 2013：拓撲測試出現問題
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
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="7fb62-102">Lync Server 2013 中的拓撲測試問題</span><span class="sxs-lookup"><span data-stu-id="7fb62-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fb62-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7fb62-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7fb62-104">就像**Test CsTopology** Cmdlet 一樣，最佳做法分析程式提供一種驗證 Lync Server 2013 在全域層級正常運作的方式。</span><span class="sxs-lookup"><span data-stu-id="7fb62-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="7fb62-105">根據預設，最佳做法分析程式（例如 Cmdlet）會檢查您的整個 Lync Server 2013 基礎結構，確認所需的服務正在執行，以及已針對這些服務及通用使用者許可權設定適當的使用者權利和許可權安裝 Lync Server 2013 時所建立的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7fb62-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="7fb62-106">除了驗證 Lync 伺服器的整體有效性之外，**測試 CsTopology**也會檢查特定服務的有效性。</span><span class="sxs-lookup"><span data-stu-id="7fb62-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="7fb62-107">如需使用 Cmdlet 來測試特定服務的詳細資料，請參閱 Lync Server 管理命令介面檔中的[測試 CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 。</span><span class="sxs-lookup"><span data-stu-id="7fb62-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="7fb62-108">使用下列資訊來協助解決您的拓撲問題。</span><span class="sxs-lookup"><span data-stu-id="7fb62-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7fb62-109">根據 Edge 伺服器的設定以及任何相關的周邊網路設定（包括防火牆設定和許可權），最佳做法分析程式可能無法存取及掃描您的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="7fb62-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="7fb62-110">如果您在掃描中包含 Edge 伺服器，且報告指出存取邊緣伺服器時發生問題，請清除 [<STRONG>邊緣伺服器</STRONG>] 核取方塊並再次執行掃描，以避免問題顯示在報表中。</span><span class="sxs-lookup"><span data-stu-id="7fb62-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="7fb62-111">解決您的拓撲問題</span><span class="sxs-lookup"><span data-stu-id="7fb62-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="7fb62-112">如果拓撲測試發現您的拓撲有問題，這些問題可能是由您發佈或啟用拓撲時所發生的問題所造成。</span><span class="sxs-lookup"><span data-stu-id="7fb62-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="7fb62-113">當您對拓撲進行變更時，變更只會在已發佈並啟用時才會生效。</span><span class="sxs-lookup"><span data-stu-id="7fb62-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="7fb62-114">您必須使用 [拓撲建立器] 來變更拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="7fb62-115">進行變更之後，您可以使用拓撲建立器來發佈及啟用這些變更。</span><span class="sxs-lookup"><span data-stu-id="7fb62-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="7fb62-116">當您發佈變更時，新的資訊（例如，新的網站或新的伺服器角色）會寫入中央管理儲存區。</span><span class="sxs-lookup"><span data-stu-id="7fb62-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="7fb62-117">不過，這些新的（或新修改的）物件不會立即加入您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="7fb62-118">只有當您啟用更新的拓撲時，物件才會加入拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="7fb62-119">如果您在拓撲建立器中選取 [發佈] 選項，則會發生上述兩個步驟：已發佈變更（也就是將它們寫入中央管理儲存區），然後啟用新的拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="7fb62-120">根據預設，RTCUniversalServerAdmins 群組的成員有權執行**Publish CsTopology** Cmdlet 和**Enable-CsTopology** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fb62-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="7fb62-121">不過，如果沒有委派設定許可權，您必須以網域管理員身分登入，才能執行**發佈 CsTopology**。</span><span class="sxs-lookup"><span data-stu-id="7fb62-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="7fb62-122">若要賦予 RTCUniversalServerAdmins 實際使用**Publish CsTopology** Cmdlet 的權利，您必須在每個包含執行 Lync Server services 的電腦的 Active Directory 容器上執行**Grant-CsSetupPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fb62-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="7fb62-123">若要賦予 RTCUniversalServerAdmins 使用**Enable CsTopology** Cmdlet 的權利，您必須針對每個包含執行 Lync Server Services 的電腦的 Active Directory 網域服務容器，執行**Set CsSetupPermission** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7fb62-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="7fb62-124">請注意，這適用于使用拓撲建立器來啟用和發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="7fb62-125">如果您沒有使用 [**設定 CsSetupPermission**] 委派許可權，只有網域管理員才能透過拓撲產生器啟用和發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="7fb62-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

