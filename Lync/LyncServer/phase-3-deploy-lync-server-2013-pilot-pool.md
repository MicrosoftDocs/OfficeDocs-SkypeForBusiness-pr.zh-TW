---
title: 階段3：部署 Lync Server 2013 試驗集區
description: 階段3：部署 Lync Server 2013 試驗集區。
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
ms.openlocfilehash: f72f0cdd2e7d3b9e29891a4adc0ab0551539f465
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571159"
---
# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="cb592-103">階段3：部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="cb592-103">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb592-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cb592-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cb592-105">本節涵蓋部署 Lync Server 2013 試驗集區所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="cb592-105">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="cb592-106">部署 Lync Server 2013 需要使用拓撲產生器來定義您的拓撲和您要部署的元件、準備部署 Lync Server 2013 元件的環境、在第一部前端伺服器上發佈拓撲設計，然後針對您的部署安裝和設定 Lync Server 2013 軟體。</span><span class="sxs-lookup"><span data-stu-id="cb592-106">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="cb592-107">完成後，您的 Lync Server 2013 試驗集區部署會與現有的 Lync Server 2010 集區共存。</span><span class="sxs-lookup"><span data-stu-id="cb592-107">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb592-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="cb592-108">In This Section</span></span>

  - [<span data-ttu-id="cb592-109">準備 Lync Server 的 Active Directory</span><span class="sxs-lookup"><span data-stu-id="cb592-109">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="cb592-110">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="cb592-110">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="cb592-111">部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="cb592-111">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="cb592-112">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="cb592-112">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="cb592-113">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="cb592-113">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="cb592-114">設定 XMPP 閘道的存取原則和憑證</span><span class="sxs-lookup"><span data-stu-id="cb592-114">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

