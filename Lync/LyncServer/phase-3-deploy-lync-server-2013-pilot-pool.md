---
title: 階段 3： 部署 Lync Server 2013 試驗集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c87be6f690c5c31822dd59bea52c9140e43a4926
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="c9b9e-102">階段 3： 部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9b9e-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9b9e-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="c9b9e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="c9b9e-104">本章節將說明部署 Lync Server 2013 試驗集區所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="c9b9e-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="c9b9e-105">Lync Server 2013 的部署需要使用拓撲產生器來定義拓撲以及您想要部署的元件準備您的環境部署的 Lync Server 2013 元件、 發佈拓撲設計上的第一個前端伺服器，以及然後安裝和設定 Lync Server 2013 軟體部署的元件。</span><span class="sxs-lookup"><span data-stu-id="c9b9e-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="c9b9e-106">完成時，Lync Server 2013 試驗集區部署將會與現有的 Lync Server 2010 集區共存。</span><span class="sxs-lookup"><span data-stu-id="c9b9e-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9b9e-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c9b9e-107">In This Section</span></span>

  - [<span data-ttu-id="c9b9e-108">準備 Lync Server 的 Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9b9e-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="c9b9e-109">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="c9b9e-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="c9b9e-110">部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="c9b9e-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="c9b9e-111">確認舊版集區與試驗集區共存</span><span class="sxs-lookup"><span data-stu-id="c9b9e-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="c9b9e-112">將試驗集區連接到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c9b9e-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="c9b9e-113">設定 XMPP 閘道存取原則及憑證</span><span class="sxs-lookup"><span data-stu-id="c9b9e-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

