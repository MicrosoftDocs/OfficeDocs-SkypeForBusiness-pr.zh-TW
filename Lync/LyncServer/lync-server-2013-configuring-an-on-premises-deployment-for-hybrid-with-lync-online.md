---
title: 設定內部部署以混合使用 Lync Online
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
ms.openlocfilehash: eda277d2be970e2495c8bb4cb1a8bd2bcb288bc9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="b22e2-102">設定內部部署以混合使用 Lync Online</span><span class="sxs-lookup"><span data-stu-id="b22e2-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b22e2-103">_**主題上次修改日期：** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="b22e2-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="b22e2-104">混合式部署是一種部署，其中有些使用者是託管于內部部署的，而有些使用者則是在線上進行的，但所有使用者都共用同一個網域，例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b22e2-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="b22e2-105">本節將引導您完成部署混合式部署所需的應用程式，然後設定您的部署來啟用它。</span><span class="sxs-lookup"><span data-stu-id="b22e2-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b22e2-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="b22e2-106">In This Section</span></span>

  - [<span data-ttu-id="b22e2-107">Lync Server 2013 混合式環境概觀</span><span class="sxs-lookup"><span data-stu-id="b22e2-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="b22e2-108">準備與部署 Lync Server 2013 混合式環境的步驟</span><span class="sxs-lookup"><span data-stu-id="b22e2-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="b22e2-109">使用 Lync Online 設定 Lync Server 2013 的同盟</span><span class="sxs-lookup"><span data-stu-id="b22e2-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="b22e2-110">在 Lync Server 2013 中設定音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="b22e2-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="b22e2-111">在 Lync Server 2013 中將使用者移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="b22e2-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="b22e2-112">在混合式 Lync Server 2013 部署中管理使用者</span><span class="sxs-lookup"><span data-stu-id="b22e2-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

