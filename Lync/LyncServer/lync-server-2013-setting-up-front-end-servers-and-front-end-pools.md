---
title: Lync Server 2013： 設定前端伺服器和前端集區
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
ms.openlocfilehash: e6f02d3af49cd6bf37764528d7c6f71c587d7d1b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="227d3-102">設定 Lync Server 2013 的前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="227d3-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="227d3-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="227d3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="227d3-104">本節會引導您完成安裝 Lync Server 2013 和設定 Standard Edition 伺服器與前端集區，包括前端伺服器和與前端伺服器組合的任何伺服器角色的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="227d3-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="227d3-105">若要安裝並設定伺服器角色，您可以執行 Lync Server 部署精靈的每部電腦上安裝伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="227d3-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="227d3-106">您可以使用 [部署精靈完成所有的四個部署步驟，包括安裝本機設定存放區、 安裝前端伺服器、 設定憑證及啟動服務。</span><span class="sxs-lookup"><span data-stu-id="227d3-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="227d3-107">您可以設定伺服器角色之前，您必須已成功發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="227d3-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="227d3-108">如需發行拓撲的詳細資訊，請參閱<A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing 和實作拓撲設計 Lync Server 2013 中</A>。</span><span class="sxs-lookup"><span data-stu-id="227d3-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="227d3-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="227d3-109">In This Section</span></span>

  - [<span data-ttu-id="227d3-110">在 Lync Server 2013 中安裝本機設定存放區</span><span class="sxs-lookup"><span data-stu-id="227d3-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="227d3-111">安裝 Lync Server 2013 的伺服器元件</span><span class="sxs-lookup"><span data-stu-id="227d3-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="227d3-112">在 Lync Server 2013 中設定伺服器憑證</span><span class="sxs-lookup"><span data-stu-id="227d3-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="227d3-113">Lync Server 2013 的伺服器上啟動服務</span><span class="sxs-lookup"><span data-stu-id="227d3-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="227d3-114">在 Lync Server 2013 中測試集區部署</span><span class="sxs-lookup"><span data-stu-id="227d3-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="227d3-115">在 Lync Server 2013 中測試 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="227d3-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

