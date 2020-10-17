---
title: Lync Server 2013：部署 Lync Server
description: Lync Server 2013：部署 Lync Server。
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
ms.openlocfilehash: 569b1e8b07954f04ee7e4f73de51494ece27157e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564169"
---
# <a name="deploying-lync-server-2013"></a><span data-ttu-id="6505d-103">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6505d-103">Deploying Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6505d-104">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6505d-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6505d-105">Lync Server 2013 的部署程式取決於您決定要安裝的 Lync Server 拓撲和元件，包括是否要部署前端集區或 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="6505d-105">Your deployment process for Lync Server 2013 is determined by the Lync Server topology and components you decide to install, including whether you want to deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="6505d-106">本節中的主題可協助您決定要部署的環境，並引導您完成部署程式。</span><span class="sxs-lookup"><span data-stu-id="6505d-106">The topics in this section help you determine what environment you want to deploy and guide you through the deployment process.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6505d-107">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6505d-107">In This Section</span></span>

  - [<span data-ttu-id="6505d-108">Lync Server 2013 的部署概況</span><span class="sxs-lookup"><span data-stu-id="6505d-108">Deployment overview for Lync Server 2013</span></span>](lync-server-2013-deployment-overview.md)

  - [<span data-ttu-id="6505d-109">Lync Server 2013 的系統需求</span><span class="sxs-lookup"><span data-stu-id="6505d-109">System requirements for Lync Server 2013</span></span>](lync-server-2013-system-requirements.md)

  - [<span data-ttu-id="6505d-110">準備 Lync Server 2013 的基礎結構和系統</span><span class="sxs-lookup"><span data-stu-id="6505d-110">Preparing the infrastructure and systems for Lync Server 2013</span></span>](lync-server-2013-preparing-the-infrastructure-and-systems.md)

  - [<span data-ttu-id="6505d-111">在 Lync Server 2013 中定義及設定拓撲</span><span class="sxs-lookup"><span data-stu-id="6505d-111">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)

  - [<span data-ttu-id="6505d-112">在 Lync Server 2013 中完成及實施拓撲設計</span><span class="sxs-lookup"><span data-stu-id="6505d-112">Finalizing and implementing the topology design in Lync Server 2013</span></span>](lync-server-2013-finalizing-and-implementing-the-topology-design.md)

  - [<span data-ttu-id="6505d-113">為 Lync Server 2013 設定前端伺服器和前端集區</span><span class="sxs-lookup"><span data-stu-id="6505d-113">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

  - [<span data-ttu-id="6505d-114">將 Lync Server 2013 Standard Edition 部署到現有的 Lync Server 2013 企業版</span><span class="sxs-lookup"><span data-stu-id="6505d-114">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>](lync-server-2013-deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise.md)

  - [<span data-ttu-id="6505d-115">在 Lync Server 2013 中新增伺服器角色</span><span class="sxs-lookup"><span data-stu-id="6505d-115">Adding server roles in Lync Server 2013</span></span>](lync-server-2013-adding-server-roles.md)

  - [<span data-ttu-id="6505d-116">在 Lync Server 2013 中設定 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="6505d-116">Setting up Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

