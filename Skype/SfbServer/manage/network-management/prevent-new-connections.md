---
title: 防止新的連線
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823463"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="aad44-102">避免伺服器維護的新連線到商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="aad44-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="aad44-103">商務用 Skype Server 可讓您讓伺服器離線 (例如，將軟體或硬體升級) 套用至不會對使用者造成任何服務。</span><span class="sxs-lookup"><span data-stu-id="aad44-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="aad44-p101">當您指定該選項以防止對集區中的伺服器進行新的連線或呼叫時，該選項會在您正式實作這個選項時停止接受任何新的連線與呼叫。這些新的連線和呼叫會路由轉送給集區中的其他伺服器。伺服器會防止新的連線進入，以讓現有連線的工作階段持續進行到自然結束為止。當所有現有的工作階段都結束時，伺服器就可以準備離線。</span><span class="sxs-lookup"><span data-stu-id="aad44-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="aad44-108">當您禁止新的前端伺服器連線時，有些商務用 Skype Server 功能和服務會依賴 DNS 負載平衡，以確保其運作正常。</span><span class="sxs-lookup"><span data-stu-id="aad44-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="aad44-109">如果您的集區沒有使用 DNS 負載平衡，透過這些服務進行的連線可能無法在伺服器阻止新的連線傳入期間，由系統重新路由傳送至其他伺服器，因此當該伺服器離線時，有些工作階段及呼叫便會中斷。</span><span class="sxs-lookup"><span data-stu-id="aad44-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="aad44-110">以下是仰賴 DNS 負載平衡以確保此選項正常運作的相關功能：</span><span class="sxs-lookup"><span data-stu-id="aad44-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="aad44-111">語音應答</span><span class="sxs-lookup"><span data-stu-id="aad44-111">Attendant</span></span>

  - <span data-ttu-id="aad44-112">Conferencing Announcement application</span><span class="sxs-lookup"><span data-stu-id="aad44-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="aad44-113">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="aad44-113">Response Group application</span></span>

  - <span data-ttu-id="aad44-114">宣告應用程式</span><span class="sxs-lookup"><span data-stu-id="aad44-114">Announcement application</span></span>

  - <span data-ttu-id="aad44-115">Call Park application</span><span class="sxs-lookup"><span data-stu-id="aad44-115">Call Park application</span></span>

<span data-ttu-id="aad44-116">如需 DNS 負載平衡的詳細資訊，請參閱 [負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="aad44-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="aad44-117">除了為執行商務用 Skype Server 的伺服器上的所有服務阻止新的連線，您也可以防止個別商務用 Skype Server 服務的新連接。</span><span class="sxs-lookup"><span data-stu-id="aad44-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="aad44-118">例如，在您需要套用商務用 Skype 伺服器更新（不需要整個伺服器關閉）的情況下，此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="aad44-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="aad44-119">請注意，當您要防止某個服務進行連線，必須選取已經顯示在 Windows 服務清單中的分組服務項目。</span><span class="sxs-lookup"><span data-stu-id="aad44-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="aad44-120">例如，商務用 Skype Server Front-End 服務和用於監控的資料收集代理程式是獨立的商務用 Skype Server 服務，但是在 Windows 服務清單中，他們會進行合併，並顯示為商務用 Skype Server 前端服務。</span><span class="sxs-lookup"><span data-stu-id="aad44-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="aad44-121">您可以防止商務用 Skype Server 前端服務的新連線，但您無法針對這兩個個別的基礎商務用 Skype Server 服務，分別防止新的連線。</span><span class="sxs-lookup"><span data-stu-id="aad44-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aad44-p104">設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。</span><span class="sxs-lookup"><span data-stu-id="aad44-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="aad44-124">若要防止新連接至商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="aad44-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="aad44-125">以 Administrators 群組成員的身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="aad44-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="aad44-126">開啟 [服務] 嵌入式管理單元主控台：按一下 [ **開始**]，指向 [ **所有程式**]，指向 [系統 **管理工具**]，然後按一下 [ **服務**]。</span><span class="sxs-lookup"><span data-stu-id="aad44-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="aad44-127">在清單中，按兩下您要防止新連線的商務用 Skype 伺服器 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="aad44-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="aad44-128">在 [內容] 對話方塊的 **[服務狀態: 已啟動]** 下方，按一下 **[暫停]**。</span><span class="sxs-lookup"><span data-stu-id="aad44-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="aad44-129">(選用，但建議) 按一下 **[啟動類型]** 旁的 **[手動]**。</span><span class="sxs-lookup"><span data-stu-id="aad44-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="aad44-p105">設定伺服器防止新連線、接著重新啟動伺服器後，依預設伺服器會在啟動後立即開始接受新連線。若要避免這種情形，請在重新啟動伺服器前，將伺服器設為僅能手動暫停和繼續。</span><span class="sxs-lookup"><span data-stu-id="aad44-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
