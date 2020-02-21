---
title: Lync Server 2013： 部署遠端呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5659bf3e210f1f8294789729a758d4877d3e70bb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="e08bc-102">部署 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e08bc-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e08bc-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="e08bc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e08bc-104">本節會引導您完成為組織中的使用者部署遠端呼叫控制功能的程序。</span><span class="sxs-lookup"><span data-stu-id="e08bc-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e08bc-105">雖然位於組織防火牆以外的遠端使用者也可使用遠端呼叫控制功能，但本文件並不提供部署外部存取案例的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e08bc-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="e08bc-106">如需部署外部使用者存取的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-external-user-access.md">Deploying Lync Server 2013 中的外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="e08bc-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e08bc-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e08bc-107">In This Section</span></span>

  - [<span data-ttu-id="e08bc-108">設定 Lync Server 2013，才能路由傳送到 SIP/CSTA 閘道</span><span class="sxs-lookup"><span data-stu-id="e08bc-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="e08bc-109">在 Lync Server 2013 中設定為遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="e08bc-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="e08bc-110">設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="e08bc-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="e08bc-111">[定義 Lync Server 2013 中的 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)（只有當閘道設定成使用 TCP）</span><span class="sxs-lookup"><span data-stu-id="e08bc-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="e08bc-112">啟用 Lync 之使用者的 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e08bc-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="e08bc-113">遠端呼叫控制和電話號碼正規化 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="e08bc-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="e08bc-114">[移除舊版授權的主機 （選用） 的 Lync Server 2013 中](lync-server-2013-remove-a-legacy-authorized-host-optional.md)（只有當您要移轉先前啟用遠端呼叫控制的使用者）</span><span class="sxs-lookup"><span data-stu-id="e08bc-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e08bc-115">相關各節</span><span class="sxs-lookup"><span data-stu-id="e08bc-115">Related Sections</span></span>

[<span data-ttu-id="e08bc-116">規劃 Lync Server 2013 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e08bc-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

