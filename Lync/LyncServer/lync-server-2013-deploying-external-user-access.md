---
title: Lync Server 2013：部署外部使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba083650b9a068d48e28bf8af0c51b4b25b5c227
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="bd398-102">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="bd398-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd398-103">_**主題上次修改日期：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="bd398-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="bd398-104">部署 Microsoft Lync Server 2013 的 edge 元件可讓未登入貴組織內部網路的外部使用者（包括經過驗證且匿名的遠端使用者、聯盟夥伴（包括 XMPP 合作夥伴））成為可能。行動用戶端與公用立即訊息（IM）服務的使用者，可使用 Lync Server 與您組織中的其他使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="bd398-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="bd398-105">Lync Server 2013 的部署與設定進程與 Lync Server 2010 沒有明顯不同。</span><span class="sxs-lookup"><span data-stu-id="bd398-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="bd398-106">安裝與管理工具的功能與 Lync Server 2010 中的功能很類似。</span><span class="sxs-lookup"><span data-stu-id="bd398-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd398-107">Microsoft Lync Server 2013&nbsp;Edge 伺服器安裝與設定可能是一個複雜的程式，需要與您的內部團隊進行大量的規劃與協調，包括–但不限於安全性、網路、防火牆、網域名稱系統（DNS）、負載平衡器，以及公開金鑰基礎結構（PKI）考慮。</span><span class="sxs-lookup"><span data-stu-id="bd398-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="bd398-108">我們強烈建議您先複習並使用所提供的規劃程式和檔，再部署您的外部存取元件。</span><span class="sxs-lookup"><span data-stu-id="bd398-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="bd398-109">這將會在您逐步完成部署程式時，協助您限制不想變更和問題的數量與頻率。</span><span class="sxs-lookup"><span data-stu-id="bd398-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="bd398-110">如需規劃外部使用者存取權的相關資訊，請參閱<A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 規劃外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="bd398-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd398-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="bd398-111">In This Section</span></span>

  - [<span data-ttu-id="bd398-112">Lync Server 2013 中外部使用者存取的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="bd398-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="bd398-113">外部使用者為 Lync Server 2013 存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="bd398-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="bd398-114">在周邊網路中準備安裝 Lync Server 2013 的伺服器</span><span class="sxs-lookup"><span data-stu-id="bd398-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="bd398-115">在 Lync Server 2013 中建置 Edge 和 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="bd398-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="bd398-116">[在 Lync Server 2013 中設定導演](lync-server-2013-setting-up-the-director.md)（選用）</span><span class="sxs-lookup"><span data-stu-id="bd398-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="bd398-117">在 Lync Server 2013 中設定 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bd398-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="bd398-118">設定 Lync Server 2013 的反向 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="bd398-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="bd398-119">在 Lync Server 2013 中設定外部使用者存取支援</span><span class="sxs-lookup"><span data-stu-id="bd398-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="bd398-120">Lync Server 2013 的 Lync-Skype 連線佈建指南</span><span class="sxs-lookup"><span data-stu-id="bd398-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="bd398-121">在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及 Public Instant Messaging</span><span class="sxs-lookup"><span data-stu-id="bd398-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="bd398-122">在 Lync Server 2013 中部署行動性</span><span class="sxs-lookup"><span data-stu-id="bd398-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="bd398-123">在 Lync Server 2013 中驗證 Edge 部署</span><span class="sxs-lookup"><span data-stu-id="bd398-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

