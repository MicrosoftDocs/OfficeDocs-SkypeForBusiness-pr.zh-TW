---
title: 設定混合式內部部署與 Lync Online
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
ms.openlocfilehash: 787286c660106a27a9b6df7d4aedb22adecfb5cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="6a23d-102">設定混合式內部部署與 Lync Online</span><span class="sxs-lookup"><span data-stu-id="6a23d-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a23d-103">_**上次修改主題：** 2014年-05-28_</span><span class="sxs-lookup"><span data-stu-id="6a23d-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="6a23d-104">混合式部署都是的部署在其中部分使用者為隸屬於內部部署和部分使用者位於線上使用，但所有使用者都共用相同的網域，例如 user@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6a23d-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="6a23d-105">本節會引導您完成部署混合式部署，所需的應用程式，然後設定您的部署，才能啟用它。</span><span class="sxs-lookup"><span data-stu-id="6a23d-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a23d-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6a23d-106">In This Section</span></span>

  - [<span data-ttu-id="6a23d-107">Lync Server 2013 混合式環境的概觀</span><span class="sxs-lookup"><span data-stu-id="6a23d-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="6a23d-108">準備和部署 Lync Server 2013 混合式環境的步驟</span><span class="sxs-lookup"><span data-stu-id="6a23d-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="6a23d-109">使用 Lync Online 設定 Lync Server 2013 的同盟</span><span class="sxs-lookup"><span data-stu-id="6a23d-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="6a23d-110">在 Lync Server 2013 中設定的音訊會議提供者的同盟</span><span class="sxs-lookup"><span data-stu-id="6a23d-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="6a23d-111">將使用者移至 Lync Online 在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a23d-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="6a23d-112">管理混合 Lync Server 2013 部署中的使用者</span><span class="sxs-lookup"><span data-stu-id="6a23d-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

