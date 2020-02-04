---
title: 階段3：部署 Lync Server 2013 試用版池
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
ms.openlocfilehash: 38a9e19ea3d9456a5e6f5b395286d77ed831f6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="0ee9c-102">階段3：部署 Lync Server 2013 試用版池</span><span class="sxs-lookup"><span data-stu-id="0ee9c-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ee9c-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0ee9c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0ee9c-104">本節涵蓋部署 Lync Server 2013 試驗池所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="0ee9c-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="0ee9c-105">部署 Lync Server 2013 需要使用拓撲建立器來定義您的拓撲及您想要部署的元件，為您的環境準備部署 Lync Server 2013 元件，在第一個前端發佈拓撲設計伺服器，然後針對您部署的元件安裝和設定 Lync Server 2013 軟體。</span><span class="sxs-lookup"><span data-stu-id="0ee9c-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="0ee9c-106">完成後，您的 Lync Server 2013 試驗池部署會與現有的 Lync Server 2010 池共存。</span><span class="sxs-lookup"><span data-stu-id="0ee9c-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ee9c-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="0ee9c-107">In This Section</span></span>

  - [<span data-ttu-id="0ee9c-108">準備 Lync Server 的 Active Directory</span><span class="sxs-lookup"><span data-stu-id="0ee9c-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="0ee9c-109">從現有部署下載拓撲</span><span class="sxs-lookup"><span data-stu-id="0ee9c-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="0ee9c-110">部署 Lync Server 2013 試用版池</span><span class="sxs-lookup"><span data-stu-id="0ee9c-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="0ee9c-111">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="0ee9c-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="0ee9c-112">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="0ee9c-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="0ee9c-113">設定 XMPP 閘道的存取原則和憑證</span><span class="sxs-lookup"><span data-stu-id="0ee9c-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

