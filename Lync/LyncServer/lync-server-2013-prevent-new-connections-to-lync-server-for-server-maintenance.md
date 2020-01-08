---
title: 防止新連線至 Lync Server 以進行伺服器維護
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="f8b07-102">防止新連線至 Lync Server 2013 以進行伺服器維護</span><span class="sxs-lookup"><span data-stu-id="f8b07-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8b07-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f8b07-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f8b07-104">Lync Server 可讓您讓伺服器離線（例如，將軟體或硬體升級套用），而不會對使用者造成任何服務遺失。</span><span class="sxs-lookup"><span data-stu-id="f8b07-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="f8b07-105">當您指定防止新連線或呼叫池中伺服器的選項時，它會在您執行此選項後立即停止進行任何新的連線與通話。</span><span class="sxs-lookup"><span data-stu-id="f8b07-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="f8b07-106">這些新的連線和通話會透過池中的其他伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="f8b07-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="f8b07-107">防止新連線的伺服器可讓其在現有連線中的會話繼續下去，直到它們自然結束為止。</span><span class="sxs-lookup"><span data-stu-id="f8b07-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="f8b07-108">當所有現有的會話都已結束時，伺服器即可離線使用。</span><span class="sxs-lookup"><span data-stu-id="f8b07-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="f8b07-109">當您禁止與前端伺服器建立新的連線時，某些 Lync Server 功能與服務會依賴 DNS 負載平衡，以確保其正常運作。</span><span class="sxs-lookup"><span data-stu-id="f8b07-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="f8b07-110">如果您不是在該池使用 DNS 負載平衡，在伺服器防範新連線的期間，透過這些服務的連線可能無法重新路由到其他伺服器，因此當伺服器離線時，可能會打斷.</span><span class="sxs-lookup"><span data-stu-id="f8b07-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="f8b07-111">依賴 DNS 負載平衡的功能，以確保此選項正常運作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f8b07-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="f8b07-112">值守</span><span class="sxs-lookup"><span data-stu-id="f8b07-112">Attendant</span></span>

  - <span data-ttu-id="f8b07-113">會議公告應用程式</span><span class="sxs-lookup"><span data-stu-id="f8b07-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="f8b07-114">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="f8b07-114">Response Group application</span></span>

  - <span data-ttu-id="f8b07-115">宣告應用程式</span><span class="sxs-lookup"><span data-stu-id="f8b07-115">Announcement application</span></span>

  - <span data-ttu-id="f8b07-116">通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="f8b07-116">Call Park application</span></span>

<span data-ttu-id="f8b07-117">如需有關 DNS 負載平衡的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="f8b07-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="f8b07-118">除了防止執行 Lync Server 的伺服器上所有服務的新連線，您也可以避免個別 Lync Server 服務的新連線。</span><span class="sxs-lookup"><span data-stu-id="f8b07-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="f8b07-119">例如，如果您需要套用不需要整個伺服器即可關閉的 Lync Server 更新，這種方法很有用。</span><span class="sxs-lookup"><span data-stu-id="f8b07-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="f8b07-120">請注意，當您禁止連線某個服務時，您必須選取已群組並顯示在 Windows 服務清單中的服務。</span><span class="sxs-lookup"><span data-stu-id="f8b07-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="f8b07-121">例如，Lync Server 前端服務和用於監視的資料收集代理程式是獨立的 Lync Server services，但在 [Windows 服務] 清單中，它們會進行整合，並顯示為 Lync Server 前端服務。</span><span class="sxs-lookup"><span data-stu-id="f8b07-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="f8b07-122">您可以防止 Lync Server 前端服務的新連線，但您無法單獨避免這兩個個別基礎 Lync 伺服器服務的新連線。</span><span class="sxs-lookup"><span data-stu-id="f8b07-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f8b07-123">當您將伺服器設定為防止新連線，然後重新開機伺服器時，伺服器會在啟動後立即開始接受新的連線。</span><span class="sxs-lookup"><span data-stu-id="f8b07-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="f8b07-124">若要避免這種情況，請在重新開機伺服器前，將伺服器設定為只暫停並手動繼續。</span><span class="sxs-lookup"><span data-stu-id="f8b07-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="f8b07-125">若要防止新連線至 Lync Server：</span><span class="sxs-lookup"><span data-stu-id="f8b07-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="f8b07-126">以管理員群組的成員身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="f8b07-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="f8b07-127">開啟 [服務] 管理單元主控台：按一下 [**開始**]，指向 [**所有程式**]，指向 [系統**管理工具**]，然後按一下 [**服務**]。</span><span class="sxs-lookup"><span data-stu-id="f8b07-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="f8b07-128">在清單中，按兩下您要防止新連接的 Lync Server Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="f8b07-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="f8b07-129">在 [內容] 對話方塊中的 [**服務狀態：已啟動**] 底下，按一下 [**暫停**]。</span><span class="sxs-lookup"><span data-stu-id="f8b07-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="f8b07-130">或者，您可以選擇 [**啟動類型**] 旁的 [**手動**]，然後按一下 [建議]。</span><span class="sxs-lookup"><span data-stu-id="f8b07-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="f8b07-131">當您將伺服器設定為防止新連線，然後重新開機伺服器時，伺服器會在啟動後立即開始接受新的連線。</span><span class="sxs-lookup"><span data-stu-id="f8b07-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="f8b07-132">若要避免這種情況，請在重新開機伺服器前，將伺服器設定為只暫停並手動繼續。</span><span class="sxs-lookup"><span data-stu-id="f8b07-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="f8b07-133">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8b07-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

