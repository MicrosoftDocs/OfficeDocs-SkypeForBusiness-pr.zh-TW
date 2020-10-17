---
title: Lync Server 2013：部署遠端呼叫控制
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
ms.openlocfilehash: 9d4e388898b36f2eae913a5c34e11119cf95402a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520030"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="e0c87-102">在 Lync Server 2013 中部署遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e0c87-102">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0c87-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="e0c87-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="e0c87-104">本節會引導您完成為組織中的使用者部署遠端呼叫控制功能的程序。</span><span class="sxs-lookup"><span data-stu-id="e0c87-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0c87-105">雖然位於組織防火牆以外的遠端使用者也可使用遠端呼叫控制功能，但本文件並不提供部署外部存取案例的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e0c87-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="e0c87-106">如需部署外部使用者存取的詳細資訊，請參閱部署檔中的部署 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的外部使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="e0c87-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0c87-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e0c87-107">In This Section</span></span>

  - [<span data-ttu-id="e0c87-108">設定 Lync Server 2013 以路由傳送至 SIP/CSTA 閘道</span><span class="sxs-lookup"><span data-stu-id="e0c87-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="e0c87-109">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="e0c87-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="e0c87-110">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="e0c87-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="e0c87-111">只有在閘道設定為使用 TCP 時，才[在 Lync Server 2013 (中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)) </span><span class="sxs-lookup"><span data-stu-id="e0c87-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="e0c87-112">在 Lync Server 2013 中啟用 Lync 使用者的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e0c87-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="e0c87-113">Lync Server 2013 的遠端呼叫控制和電話號碼正規化</span><span class="sxs-lookup"><span data-stu-id="e0c87-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="e0c87-114">只有在遷移先前為遠端呼叫控制啟用的使用者時，才[在 Lync Server 2013 中移除舊版授權主機 (選用) ](lync-server-2013-remove-a-legacy-authorized-host-optional.md) () </span><span class="sxs-lookup"><span data-stu-id="e0c87-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e0c87-115">相關各節</span><span class="sxs-lookup"><span data-stu-id="e0c87-115">Related Sections</span></span>

[<span data-ttu-id="e0c87-116">在 Lync Server 2013 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="e0c87-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

