---
title: Lync Server 2013：部署遠端呼叫控制
description: Lync Server 2013：部署遠端呼叫控制。
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
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566079"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="ff1c9-103">在 Lync Server 2013 中部署遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="ff1c9-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff1c9-104">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ff1c9-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ff1c9-105">本節會引導您完成為組織中的使用者部署遠端呼叫控制功能的程序。</span><span class="sxs-lookup"><span data-stu-id="ff1c9-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff1c9-106">雖然位於組織防火牆以外的遠端使用者也可使用遠端呼叫控制功能，但本文件並不提供部署外部存取案例的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ff1c9-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="ff1c9-107">如需部署外部使用者存取的詳細資訊，請參閱部署檔中的部署 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的外部使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="ff1c9-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff1c9-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ff1c9-108">In This Section</span></span>

  - [<span data-ttu-id="ff1c9-109">設定 Lync Server 2013 以路由傳送至 SIP/CSTA 閘道</span><span class="sxs-lookup"><span data-stu-id="ff1c9-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="ff1c9-110">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="ff1c9-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="ff1c9-111">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="ff1c9-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="ff1c9-112">只有在閘道設定為使用 TCP 時，才[在 Lync Server 2013 (中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)) </span><span class="sxs-lookup"><span data-stu-id="ff1c9-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="ff1c9-113">在 Lync Server 2013 中啟用 Lync 使用者的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="ff1c9-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="ff1c9-114">Lync Server 2013 的遠端呼叫控制和電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="ff1c9-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="ff1c9-115">只有在遷移先前為遠端呼叫控制啟用的使用者時，才[在 Lync Server 2013 中移除舊版授權主機 (選用) ](lync-server-2013-remove-a-legacy-authorized-host-optional.md) () </span><span class="sxs-lookup"><span data-stu-id="ff1c9-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="ff1c9-116">相關各節</span><span class="sxs-lookup"><span data-stu-id="ff1c9-116">Related Sections</span></span>

[<span data-ttu-id="ff1c9-117">在 Lync Server 2013 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="ff1c9-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

