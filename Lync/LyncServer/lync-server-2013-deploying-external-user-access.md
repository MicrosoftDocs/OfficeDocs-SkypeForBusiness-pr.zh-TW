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
ms.openlocfilehash: d1878b011ce62ff732f9b31fb905c012872fe743
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525310"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="88612-102">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="88612-102">Deploying external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88612-103">_**主題上次修改日期：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="88612-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="88612-104">2013針對未登入您組織內部網路的外部使用者（包括已驗證和匿名的遠端使用者）部署 edge 元件，可讓未登入組織內部網路的外部使用者使用 Lync Server， (包括 XMPP 夥伴) 、行動用戶端和公用立即訊息 (IM) 服務的使用者，才能與組織中的其他使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="88612-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="88612-105">Lync Server 2013 的部署和設定程式與 Lync Server 2010 不會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="88612-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="88612-106">安裝和管理的工具與 Lync Server 2010 中的功能非常相同。</span><span class="sxs-lookup"><span data-stu-id="88612-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88612-107">Microsoft Lync Server 2013 &nbsp; Edge server 安裝和設定可能是複雜的程式，需要對您的內部小組進行大量的規劃與協調，包括（但不限於）安全性、網路、防火牆、網域名稱系統 (DNS) 、負載平衡器及公開金鑰基礎結構 (PKI) 考慮。</span><span class="sxs-lookup"><span data-stu-id="88612-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="88612-108">強烈建議您檢查並使用所提供的規劃程式及檔，再部署外部存取元件。</span><span class="sxs-lookup"><span data-stu-id="88612-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="88612-109">在您進行部署程式時，這會協助限制不想要的變更和問題的數量和頻率。</span><span class="sxs-lookup"><span data-stu-id="88612-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="88612-110">如需規劃外部使用者存取的詳細資訊，請參閱 <A href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中規劃外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="88612-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88612-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="88612-111">In This Section</span></span>

  - [<span data-ttu-id="88612-112">Lync Server 2013 中外部使用者存取的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="88612-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="88612-113">Lync Server 2013 之外部使用者存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="88612-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="88612-114">準備 Lync Server 2013 周邊網路中的伺服器安裝</span><span class="sxs-lookup"><span data-stu-id="88612-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="88612-115">在 Lync Server 2013 中建立 edge 和 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="88612-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="88612-116">[在 Lync Server 2013 中設定 Director](lync-server-2013-setting-up-the-director.md) (選用) </span><span class="sxs-lookup"><span data-stu-id="88612-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="88612-117">在 Lync Server 2013 中設定 Edge server</span><span class="sxs-lookup"><span data-stu-id="88612-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="88612-118">設定 Lync Server 2013 的反向 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="88612-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="88612-119">在 Lync Server 2013 中設定外部使用者存取的支援</span><span class="sxs-lookup"><span data-stu-id="88612-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="88612-120">Lync Server 2013 中的 Lync-Skype 連線布配指南</span><span class="sxs-lookup"><span data-stu-id="88612-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="88612-121">在 Lync Server 2013 中設定 SIP 同盟、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="88612-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="88612-122">在 Lync Server 2013 中部署行動性</span><span class="sxs-lookup"><span data-stu-id="88612-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="88612-123">在 Lync Server 2013 中驗證 edge 部署</span><span class="sxs-lookup"><span data-stu-id="88612-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

