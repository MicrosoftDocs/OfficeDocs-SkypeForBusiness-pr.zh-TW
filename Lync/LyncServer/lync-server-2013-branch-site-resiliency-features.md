---
title: Lync Server 2013： 分支網站彈性功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="2f0b6-102">Lync Server 2013 中的分支網站恢復功能</span><span class="sxs-lookup"><span data-stu-id="2f0b6-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f0b6-103">_**上次修改主題：** 2014年-02-10_</span><span class="sxs-lookup"><span data-stu-id="2f0b6-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="2f0b6-104">如果您提供分支網站恢復能力，如果分支站台的 WAN 連線至中央網站失敗或無法連線到中央網站時，以下語音功能應可繼續運作：</span><span class="sxs-lookup"><span data-stu-id="2f0b6-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="2f0b6-105">輸入和輸出公用交換的電話網路 (PSTN) 通話</span><span class="sxs-lookup"><span data-stu-id="2f0b6-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="2f0b6-106">相同與不同的網站之間的使用者，皆可進行企業通話</span><span class="sxs-lookup"><span data-stu-id="2f0b6-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="2f0b6-107">基本通話處理，包括通話保留、取回和轉接</span><span class="sxs-lookup"><span data-stu-id="2f0b6-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="2f0b6-108">若為雙方立即訊息</span><span class="sxs-lookup"><span data-stu-id="2f0b6-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="2f0b6-109">來電轉接、 同時響鈴端點、 通話委派及小組通話服務，但僅限委託人和代理人 （例如，經理和經理的系統管理員） 或所有小組成員，在相同站台設定</span><span class="sxs-lookup"><span data-stu-id="2f0b6-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="2f0b6-110">詳細通話記錄 (Cdr)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="2f0b6-111">PSTN 電話撥入式會議與會議自動語音應答</span><span class="sxs-lookup"><span data-stu-id="2f0b6-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="2f0b6-112">語音信箱功能，如果您設定語音信箱重新路由設定。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="2f0b6-113">（如需詳細資訊，請參閱[Lync Server 2013 的分支網站恢復能力需求](lync-server-2013-branch-site-resiliency-requirements.md)）。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="2f0b6-114">使用者驗證和授權</span><span class="sxs-lookup"><span data-stu-id="2f0b6-114">User authentication and authorization</span></span>

<span data-ttu-id="2f0b6-115">下列功能會變成可用只有在您的恢復解決方案為分支網站的完整規模 Lync Server 部署：</span><span class="sxs-lookup"><span data-stu-id="2f0b6-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="2f0b6-116">IM、 web 和 A / V 會議</span><span class="sxs-lookup"><span data-stu-id="2f0b6-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="2f0b6-117">目前狀態和不打擾 DND 基礎路由 （可防止來電在已啟動 DND 的分機上響起）</span><span class="sxs-lookup"><span data-stu-id="2f0b6-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="2f0b6-118">更新來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="2f0b6-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="2f0b6-119">回應群組應用程式和通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="2f0b6-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="2f0b6-120">佈建新電話與用戶端，但是只有 Active Directory 網域服務有分支網站。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="2f0b6-121">增強型的 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="2f0b6-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="2f0b6-122">如果部署 E9-1-1，且 SIP 主幹在中央網站無法使用，因為在 WAN 連結已關閉，Survivable Branch Appliance 會路由傳送至本機分支閘道的 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="2f0b6-123">若要啟用此功能，在分支網站使用者的語音原則應該將通話路由傳送至本機閘道 WAN 故障時。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f0b6-124">不支援 XMPP 的 SBA (survivable branch office)。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="2f0b6-125">使用者位於 SBA 設定將無法傳送 Im 或查看與 XMPP 連絡人的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="2f0b6-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

