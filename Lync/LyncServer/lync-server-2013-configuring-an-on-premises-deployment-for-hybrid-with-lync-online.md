---
title: 使用 Lync Online 設定混合式內部部署以進行混合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises deployment for hybrid with Lync Online
ms:assetid: c26addb0-2936-4eea-9071-3ab95825154b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205237(v=OCS.15)
ms:contentKeyID: 48185321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dae2fadbfa9a51d322189be028d835432c796d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517620"
---
# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="abf28-102">使用 Lync Online 設定混合式內部部署以進行混合</span><span class="sxs-lookup"><span data-stu-id="abf28-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abf28-103">_**主題上次修改日期：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="abf28-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="abf28-104">混合式部署是一種部署方式，其中有些使用者是在內部部署中，有些使用者則是在線上，但所有使用者都共用相同的網域，例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="abf28-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="abf28-105">本節會引導您部署混合部署所需的應用程式，然後設定部署以加以啟用。</span><span class="sxs-lookup"><span data-stu-id="abf28-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abf28-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="abf28-106">In This Section</span></span>

  - [<span data-ttu-id="abf28-107">Lync Server 2013 混合式環境的概述</span><span class="sxs-lookup"><span data-stu-id="abf28-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="abf28-108">準備及部署 Lync Server 2013 混合式環境的步驟</span><span class="sxs-lookup"><span data-stu-id="abf28-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="abf28-109">設定 Lync Server 2013 與 Lync Online 的同盟</span><span class="sxs-lookup"><span data-stu-id="abf28-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="abf28-110">在 Lync Server 2013 中設定音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="abf28-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="abf28-111">在 Lync Server 2013 中將使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="abf28-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="abf28-112">在混合 Lync Server 2013 部署中管理使用者</span><span class="sxs-lookup"><span data-stu-id="abf28-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

