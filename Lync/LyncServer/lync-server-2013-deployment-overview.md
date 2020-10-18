---
title: Lync Server 2013：部署概述
description: Lync Server 2013：部署概述。
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
ms.openlocfilehash: 5bb3bac4261783a765b64ab2e81adb107599496b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575749"
---
# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="e91c6-103">Lync Server 2013 的部署概況</span><span class="sxs-lookup"><span data-stu-id="e91c6-103">Deployment overview for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e91c6-104">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e91c6-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e91c6-105">Lync Server 2013 Enterprise Edition 和 Lync Server 2013 Standard Edition 兩者之間的主要差異是，Standard Edition 不支援 Enterprise Edition 中包含的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="e91c6-105">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="e91c6-106">若要取得高可用性，您必須將多部前端伺服器部署至集區，然後才能鏡像執行 SQL Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e91c6-106">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="e91c6-107">搭配 Enterprise Edition，您可以選擇組合或定義獨立的轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="e91c6-107">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="e91c6-108">監控伺服器和封存伺服器可以使用執行 SQL Server 的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="e91c6-108">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="e91c6-109">您也可以在資料庫伺服器上執行前端伺服器及集區的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="e91c6-109">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="e91c6-110">執行 Lync Server 2013 Standard Edition 的伺服器是針對小型組織和遠端位置所設計，其地理位置是從組織的主要部署中移除。</span><span class="sxs-lookup"><span data-stu-id="e91c6-110">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="e91c6-111">兩個搭配搭配搭配進行容錯移轉的 Standard Edition server servers，在發生災難時，可支援最多5000的使用者。</span><span class="sxs-lookup"><span data-stu-id="e91c6-111">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="e91c6-112">您無法將 Standard Edition 伺服器集在一起，像是 Enterprise Edition 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e91c6-112">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="e91c6-113">此外，Standard Edition 所用的 SQL Server 資料庫也是一個執行 SQL Server Express 的組合伺服器，其設計目的是用來處理 Standard Edition Server 工作負載。</span><span class="sxs-lookup"><span data-stu-id="e91c6-113">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="e91c6-114">這不是說所有角色都必須位於 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="e91c6-114">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="e91c6-115">您可以有獨立的轉送伺服器和 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="e91c6-115">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="e91c6-116">中央管理存放區的 SQL Server 資料庫和 Lync Server 2013 的目的，必須位於執行 SQL Server 之伺服器的 Standard Edition Server 組合上。</span><span class="sxs-lookup"><span data-stu-id="e91c6-116">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="e91c6-117">監控伺服器和封存伺服器會搭配使用 SQL Server 資料庫的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="e91c6-117">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

