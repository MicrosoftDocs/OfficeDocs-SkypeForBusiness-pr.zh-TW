---
title: Lync Server 2013： 部署 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013
ms:assetid: b76795a4-4e71-4c70-a5c0-d1197fa8028c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412892(v=OCS.15)
ms:contentKeyID: 48185197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6417bb647faec4a493c124e776d519e136b0f77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013"></a><span data-ttu-id="efdb0-102">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efdb0-102">Deploying Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efdb0-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="efdb0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="efdb0-104">Lync Server 2013 的部署程序取決於您決定要安裝的元件與 Lync Server 拓撲包括是否要為前端集區或 Standard Edition server 部署。</span><span class="sxs-lookup"><span data-stu-id="efdb0-104">Your deployment process for Lync Server 2013 is determined by the Lync Server topology and components you decide to install, including whether you want to deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="efdb0-105">本節中的主題可協助您決定的環境您想要部署及引導您完成部署處理程序。</span><span class="sxs-lookup"><span data-stu-id="efdb0-105">The topics in this section help you determine what environment you want to deploy and guide you through the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efdb0-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="efdb0-106">In This Section</span></span>

  - [<span data-ttu-id="efdb0-107">Lync Server 2013 的部署概觀</span><span class="sxs-lookup"><span data-stu-id="efdb0-107">Deployment overview for Lync Server 2013</span></span>](lync-server-2013-deployment-overview.md)

  - [<span data-ttu-id="efdb0-108">Lync Server 2013 的系統需求</span><span class="sxs-lookup"><span data-stu-id="efdb0-108">System requirements for Lync Server 2013</span></span>](lync-server-2013-system-requirements.md)

  - [<span data-ttu-id="efdb0-109">準備 Lync Server 2013 系統與基礎結構</span><span class="sxs-lookup"><span data-stu-id="efdb0-109">Preparing the infrastructure and systems for Lync Server 2013</span></span>](lync-server-2013-preparing-the-infrastructure-and-systems.md)

  - [<span data-ttu-id="efdb0-110">定義和設定 Lync Server 2013 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="efdb0-110">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)

  - [<span data-ttu-id="efdb0-111">完成和 Lync Server 2013 中實作拓撲設計</span><span class="sxs-lookup"><span data-stu-id="efdb0-111">Finalizing and implementing the topology design in Lync Server 2013</span></span>](lync-server-2013-finalizing-and-implementing-the-topology-design.md)

  - [<span data-ttu-id="efdb0-112">設定 Lync Server 2013 的前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="efdb0-112">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

  - [<span data-ttu-id="efdb0-113">將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 Enterprise</span><span class="sxs-lookup"><span data-stu-id="efdb0-113">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>](lync-server-2013-deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise.md)

  - [<span data-ttu-id="efdb0-114">在 Lync Server 2013 中新增伺服器角色</span><span class="sxs-lookup"><span data-stu-id="efdb0-114">Adding server roles in Lync Server 2013</span></span>](lync-server-2013-adding-server-roles.md)

  - [<span data-ttu-id="efdb0-115">設定 Lync Server 2013 中的 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="efdb0-115">Setting up Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

