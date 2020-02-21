---
title: Lync Server 2013： 部署概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="82db4-102">Lync Server 2013 的部署概觀</span><span class="sxs-lookup"><span data-stu-id="82db4-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82db4-103">_**上次修改主題：** 2013年-03-12_</span><span class="sxs-lookup"><span data-stu-id="82db4-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="82db4-104">Lync Server 2013 Enterprise Edition 與 Lync Server 2013 Standard Edition 的主要差異是，Standard Edition 不支援 Enterprise Edition 隨附的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="82db4-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="82db4-105">高可用性，您需要部署多部前端伺服器集區，然後您可以鏡像執行 SQL Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="82db4-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="82db4-106">企業版，您可以選擇將組合在一起，或定義獨立中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="82db4-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="82db4-107">監控伺服器和封存伺服器可以使用執行 SQL Server 在獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="82db4-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="82db4-108">或者，他們可以執行資料庫伺服器上的前端伺服器和集區的 SQL Server 執行個體。</span><span class="sxs-lookup"><span data-stu-id="82db4-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="82db4-109">執行 Lync Server 2013 Standard Edition 伺服器被適用於小型組織和遠端位置] 中，依地理位置移除組織的主要部署。</span><span class="sxs-lookup"><span data-stu-id="82db4-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="82db4-110">成對發生災害時容錯移轉的兩個 Standard Edition server 伺服器可支援最多 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="82db4-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="82db4-111">您無法在像可以中 Enterprise Edition 前端伺服器集區 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="82db4-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="82db4-112">此外，Standard Edition 使用 SQL Server 資料庫已組合的伺服器執行 SQL Server Express 是設計用來處理 Standard Edition server 工作負載。</span><span class="sxs-lookup"><span data-stu-id="82db4-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="82db4-113">這並不是說的所有角色都必須都位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="82db4-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="82db4-114">您可以獨立中繼伺服器和 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="82db4-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="82db4-115">都必須位於 Standard Edition 伺服器組合與執行 SQL Server 之伺服器上的 SQL Server 資料庫的中央管理存放區和 Lync Server 2013 的目的。</span><span class="sxs-lookup"><span data-stu-id="82db4-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="82db4-116">封存伺服器與監控伺服器搭配 SQL Server 資料庫的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="82db4-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

