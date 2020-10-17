---
title: Lync Server 2013：分支網站恢復功能
description: Lync Server 2013：分支網站恢復功能。
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
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552199"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="3d81f-103">Lync Server 2013 中的分支網站恢復功能</span><span class="sxs-lookup"><span data-stu-id="3d81f-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d81f-104">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="3d81f-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="3d81f-105">如果您提供分支網站恢復能力，當分支網站與中央網站的 WAN 連線失敗，或是無法存取中央網站時，下列語音功能應該仍然可用：</span><span class="sxs-lookup"><span data-stu-id="3d81f-105">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="3d81f-106">輸入和輸出公用交換電話網路 (PSTN) 通話</span><span class="sxs-lookup"><span data-stu-id="3d81f-106">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="3d81f-107">相同與不同的網站之間的使用者，皆可進行企業通話</span><span class="sxs-lookup"><span data-stu-id="3d81f-107">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="3d81f-108">基本通話處理，包括通話保留、取回和轉接</span><span class="sxs-lookup"><span data-stu-id="3d81f-108">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="3d81f-109">兩方立即訊息</span><span class="sxs-lookup"><span data-stu-id="3d81f-109">Two-party instant messaging</span></span>

  - <span data-ttu-id="3d81f-110">來電轉接、端點同時響鈴、呼叫委派及小組通話服務，但只有在 delegator 和代理人 (例如，管理員和管理員的系統管理員) 或所有小組成員，都是在相同的網站上設定</span><span class="sxs-lookup"><span data-stu-id="3d81f-110">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="3d81f-111">Cdr)  (詳細通話記錄</span><span class="sxs-lookup"><span data-stu-id="3d81f-111">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="3d81f-112">使用會議自動語音應答的 PSTN 電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="3d81f-112">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="3d81f-113">語音信箱功能（如果您設定語音信箱重新路由設定）。</span><span class="sxs-lookup"><span data-stu-id="3d81f-113">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="3d81f-114"> (如需詳細資訊，請參閱 [Lync Server 2013 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="3d81f-114">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="3d81f-115">使用者驗證和授權</span><span class="sxs-lookup"><span data-stu-id="3d81f-115">User authentication and authorization</span></span>

<span data-ttu-id="3d81f-116">下列功能只有在您的恢復解決方案在分支網站上是完整的 Lync Server 部署時才會使用：</span><span class="sxs-lookup"><span data-stu-id="3d81f-116">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="3d81f-117">IM、web 及 A/V 會議</span><span class="sxs-lookup"><span data-stu-id="3d81f-117">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="3d81f-118">目前狀態和請勿打擾 (DND) 型路由 (禁止通話在已啟用 DND 的分機上響鈴) </span><span class="sxs-lookup"><span data-stu-id="3d81f-118">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="3d81f-119">更新來電轉接設定</span><span class="sxs-lookup"><span data-stu-id="3d81f-119">Updating call forwarding settings</span></span>

  - <span data-ttu-id="3d81f-120">回應群組應用程式和通話駐留應用程式</span><span class="sxs-lookup"><span data-stu-id="3d81f-120">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="3d81f-121">布建新的電話和用戶端，但只有在分支網站有 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="3d81f-121">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="3d81f-122">增強型 9-1-1 (E9-1-1) </span><span class="sxs-lookup"><span data-stu-id="3d81f-122">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="3d81f-123">如果已部署 E9-1-1，而中央網站的 SIP 主幹無法使用，因為 WAN 連結已關機，則 Survivable Branch 裝置會將 E9-1-1 呼叫路由傳送至本機分支閘道。</span><span class="sxs-lookup"><span data-stu-id="3d81f-123">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="3d81f-124">若要啟用此功能，分支網站使用者的語音原則應該會在發生 WAN 失敗時，將通話路由傳送至本地閘道。</span><span class="sxs-lookup"><span data-stu-id="3d81f-124">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d81f-125">SBA (survivable branch office) 不支援 XMPP。</span><span class="sxs-lookup"><span data-stu-id="3d81f-125">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="3d81f-126">位於 SBA 設定中的使用者將無法使用 XMPP 連絡人傳送 IMs 或查看顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="3d81f-126">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

