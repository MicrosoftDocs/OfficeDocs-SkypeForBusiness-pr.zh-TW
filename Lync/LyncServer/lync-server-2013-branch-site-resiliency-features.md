---
title: Lync Server 2013：分支網站彈性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="73285-102">Lync Server 2013 中的分支網站彈性功能</span><span class="sxs-lookup"><span data-stu-id="73285-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73285-103">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="73285-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="73285-104">如果您提供分支網站復原功能，且分支網站與中央網站的 WAN 連線失敗，或是無法取得中心網站，下列語音功能應該會繼續提供：</span><span class="sxs-lookup"><span data-stu-id="73285-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="73285-105">輸入和輸出公用電話網絡（PSTN）通話</span><span class="sxs-lookup"><span data-stu-id="73285-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="73285-106">在相同網站和兩個不同網站之間的使用者之間的企業通話</span><span class="sxs-lookup"><span data-stu-id="73285-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="73285-107">基本呼叫處理，包括呼叫保留、檢索及轉移</span><span class="sxs-lookup"><span data-stu-id="73285-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="73285-108">二方立即訊息</span><span class="sxs-lookup"><span data-stu-id="73285-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="73285-109">來電轉接、同時撥打端點、呼叫委派及小組通話服務，但僅限在相同的網站上設定 delegator 與代理人（例如，主管和主管管理員）或所有團隊成員</span><span class="sxs-lookup"><span data-stu-id="73285-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="73285-110">通話明細記錄（CDRs）</span><span class="sxs-lookup"><span data-stu-id="73285-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="73285-111">含會議自動助理的 PSTN 電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="73285-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="73285-112">語音信箱功能（如果您設定 [語音信箱重新路由設定]）。</span><span class="sxs-lookup"><span data-stu-id="73285-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="73285-113">（如需詳細資訊，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)）。</span><span class="sxs-lookup"><span data-stu-id="73285-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="73285-114">使用者驗證與授權</span><span class="sxs-lookup"><span data-stu-id="73285-114">User authentication and authorization</span></span>

<span data-ttu-id="73285-115">只有當您的復原方案是分支網站上的完整 Lync Server 部署時，才能使用下列功能：</span><span class="sxs-lookup"><span data-stu-id="73285-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="73285-116">IM、網站和 A/V 會議</span><span class="sxs-lookup"><span data-stu-id="73285-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="73285-117">[目前狀態] 和 [請勿打擾（DND）] 路由（在這種情況下，禁止通話在已 DND 啟用的分機上響鈴）</span><span class="sxs-lookup"><span data-stu-id="73285-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="73285-118">更新來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="73285-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="73285-119">回應群組應用程式及通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="73285-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="73285-120">提供新的手機和用戶端，但只有在分支網站中存在 Active Directory 網域服務時才有這個功能。</span><span class="sxs-lookup"><span data-stu-id="73285-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="73285-121">增強型9-1-1 （E9-1-1）</span><span class="sxs-lookup"><span data-stu-id="73285-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="73285-122">如果已部署 E9-1-1，且中央網站上的 SIP 幹線無法使用，因為 WAN 連結已關閉，所以 Survivable 分支裝置會將 E9-1-1 呼叫路由到本機分支閘道。</span><span class="sxs-lookup"><span data-stu-id="73285-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="73285-123">若要啟用此功能，分支網站使用者的語音原則應該在 WAN 發生故障時將呼叫路由到本機閘道。</span><span class="sxs-lookup"><span data-stu-id="73285-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73285-124">XMPP 不支援 SBA （survivable branch office）。</span><span class="sxs-lookup"><span data-stu-id="73285-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="73285-125">駐留在 SBA 配置中的使用者將無法使用 XMPP 連絡人傳送 Im 或查看目前狀態。</span><span class="sxs-lookup"><span data-stu-id="73285-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

