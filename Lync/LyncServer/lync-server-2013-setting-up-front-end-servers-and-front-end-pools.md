---
title: Lync Server 2013：設定前端伺服器和前端集區
description: Lync Server 2013：設定前端伺服器和前端集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d746bf342f6937c068e32caddd484b708a123910
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577239"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="074fe-103">為 Lync Server 2013 設定前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="074fe-103">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="074fe-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="074fe-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="074fe-105">本節會逐步引導您安裝 Lync Server 2013，並設定 Standard Edition server 和前端集區的伺服器角色，包括前端伺服器及與前端伺服器組合的任何伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="074fe-105">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="074fe-106">若要安裝及設定伺服器角色，請在要安裝伺服器角色的每一部電腦上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="074fe-106">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="074fe-107">您可以使用部署嚮導完成所有四個部署步驟，包括安裝本機設定存放區、安裝前端伺服器、設定憑證及啟動服務。</span><span class="sxs-lookup"><span data-stu-id="074fe-107">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="074fe-108">在您可以設定伺服器角色之前，您必須已成功發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="074fe-108">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="074fe-109">如需有關發行拓撲的詳細資訊，請參閱 <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">在 Lync Server 2013 中完成並執行拓撲設計</A>。</span><span class="sxs-lookup"><span data-stu-id="074fe-109">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="074fe-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="074fe-110">In This Section</span></span>

  - [<span data-ttu-id="074fe-111">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="074fe-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="074fe-112">安裝 Lync Server 2013 的伺服器元件</span><span class="sxs-lookup"><span data-stu-id="074fe-112">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="074fe-113">在 Lync Server 2013 中設定伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="074fe-113">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="074fe-114">在 Lync Server 2013 的伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="074fe-114">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="074fe-115">在 Lync Server 2013 中測試集區部署</span><span class="sxs-lookup"><span data-stu-id="074fe-115">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="074fe-116">在 Lync Server 2013 中測試 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="074fe-116">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

