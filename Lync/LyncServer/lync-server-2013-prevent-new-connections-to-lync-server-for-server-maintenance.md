---
title: 避免伺服器維護的新連線至 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1881050e5226df9c36d3b92194e27e1123df13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513260"
---
# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="c6a67-102">避免伺服器維護的新連線至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6a67-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6a67-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c6a67-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c6a67-104">Lync Server 可讓您讓伺服器離線 (例如，將軟體或硬體升級) 套用至不會對使用者造成任何服務。</span><span class="sxs-lookup"><span data-stu-id="c6a67-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="c6a67-p101">當您指定該選項以防止對集區中的伺服器進行新的連線或呼叫時，該選項會在您正式實作這個選項時停止接受任何新的連線與呼叫。這些新的連線和呼叫會路由轉送給集區中的其他伺服器。伺服器會防止新的連線進入，以讓現有連線的工作階段持續進行到自然結束為止。當所有現有的工作階段都結束時，伺服器就可以準備離線。</span><span class="sxs-lookup"><span data-stu-id="c6a67-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="c6a67-109">當您禁止新的前端伺服器連線時，某些 Lync Server 功能和服務會依賴 DNS 負載平衡，以確保其運作正常。</span><span class="sxs-lookup"><span data-stu-id="c6a67-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="c6a67-110">如果您的集區沒有使用 DNS 負載平衡，透過這些服務進行的連線可能無法在伺服器阻止新的連線傳入期間，由系統重新路由傳送至其他伺服器，因此當該伺服器離線時，有些工作階段及呼叫便會中斷。</span><span class="sxs-lookup"><span data-stu-id="c6a67-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="c6a67-111">以下是仰賴 DNS 負載平衡以確保此選項正常運作的相關功能：</span><span class="sxs-lookup"><span data-stu-id="c6a67-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="c6a67-112">語音應答</span><span class="sxs-lookup"><span data-stu-id="c6a67-112">Attendant</span></span>

  - <span data-ttu-id="c6a67-113">Conferencing Announcement application</span><span class="sxs-lookup"><span data-stu-id="c6a67-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="c6a67-114">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="c6a67-114">Response Group application</span></span>

  - <span data-ttu-id="c6a67-115">宣告應用程式</span><span class="sxs-lookup"><span data-stu-id="c6a67-115">Announcement application</span></span>

  - <span data-ttu-id="c6a67-116">Call Park application</span><span class="sxs-lookup"><span data-stu-id="c6a67-116">Call Park application</span></span>

<span data-ttu-id="c6a67-117">如需 DNS 負載平衡的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 DNS 負載平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="c6a67-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="c6a67-118">除了防止執行 Lync Server 之伺服器上的所有服務的新連線，您也可以防止個別 Lync Server 服務的新連線。</span><span class="sxs-lookup"><span data-stu-id="c6a67-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="c6a67-119">例如，在您需要套用 Lync Server 更新（不需要整個伺服器關閉）的情況下，此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="c6a67-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="c6a67-120">請注意，當您要防止某個服務進行連線，必須選取已經顯示在 Windows 服務清單中的分組服務項目。</span><span class="sxs-lookup"><span data-stu-id="c6a67-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="c6a67-121">例如，Lync Server Front-End 服務和用於監控的資料收集代理程式是不同的 Lync Server 服務，但是在 Windows 服務清單中，他們會進行合併，並顯示為 Lync Server 前端服務。</span><span class="sxs-lookup"><span data-stu-id="c6a67-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="c6a67-122">您可以防止 Lync Server 前端服務的新連線，但您無法單獨阻止這兩個個別基礎 Lync Server 服務的新連線。</span><span class="sxs-lookup"><span data-stu-id="c6a67-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c6a67-p104">設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。</span><span class="sxs-lookup"><span data-stu-id="c6a67-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="c6a67-125">若要防止新連接至 Lync Server：</span><span class="sxs-lookup"><span data-stu-id="c6a67-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="c6a67-126">以 Administrators 群組成員的身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c6a67-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="c6a67-127">開啟 [服務] 嵌入式管理單元主控台：按一下 [ **開始**]，指向 [ **所有程式**]，指向 [系統 **管理工具**]，然後按一下 [ **服務**]。</span><span class="sxs-lookup"><span data-stu-id="c6a67-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="c6a67-128">在清單中，按兩下您要防止新連線的 Lync Server Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="c6a67-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="c6a67-129">在 [內容] 對話方塊的 **[服務狀態: 已啟動]** 下方，按一下 **[暫停]**。</span><span class="sxs-lookup"><span data-stu-id="c6a67-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="c6a67-130">(選用，但建議) 按一下 **[啟動類型]** 旁的 **[手動]**。</span><span class="sxs-lookup"><span data-stu-id="c6a67-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="c6a67-p105">設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。</span><span class="sxs-lookup"><span data-stu-id="c6a67-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="c6a67-133">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c6a67-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

