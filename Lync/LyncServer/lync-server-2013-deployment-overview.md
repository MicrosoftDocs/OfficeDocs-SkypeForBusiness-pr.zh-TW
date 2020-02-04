---
title: Lync Server 2013：部署概觀
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
ms.openlocfilehash: 3d237e0ba3f94f81ce3988e2ce8994d49f97087d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="9047e-102">Lync Server 2013 的部署概觀</span><span class="sxs-lookup"><span data-stu-id="9047e-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9047e-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="9047e-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="9047e-104">Lync Server 2013 企業版和 Lync Server 2013 標準版之間的主要差異是，標準版不支援企業版中包含的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="9047e-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="9047e-105">為了提供高可用性，您需要將多個前端伺服器部署到一個池，然後您可以鏡像執行 SQL Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9047e-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="9047e-106">在企業版中，您可以選擇 collocate 或定義獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="9047e-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="9047e-107">[監視伺服器] 與 [封存伺服器] 可以使用執行 SQL Server 的獨立伺服器。</span><span class="sxs-lookup"><span data-stu-id="9047e-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="9047e-108">或者，他們可以在資料庫伺服器上執行前端伺服器和池的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="9047e-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="9047e-109">執行 Lync Server 2013 標準版的伺服器適用于較小的組織和遠端位置，這些位址會從組織的主要部署中移除。</span><span class="sxs-lookup"><span data-stu-id="9047e-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="9047e-110">將兩個標準版伺服器伺服器整合在一起進行，以進行容錯移轉，以避免災難情況最多可支援5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="9047e-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="9047e-111">您無法將標準版伺服器池化，就像您可以在企業版中前端伺服器一樣。</span><span class="sxs-lookup"><span data-stu-id="9047e-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="9047e-112">此外，標準版版本所使用的 SQL Server 資料庫是執行 SQL Server Express 的 collocated 伺服器，該伺服器是專為處理標準版伺服器工作負載而設計的。</span><span class="sxs-lookup"><span data-stu-id="9047e-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="9047e-113">這不是說所有角色都必須駐留在標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="9047e-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="9047e-114">您可以有獨立的中繼伺服器與 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9047e-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="9047e-115">[中央管理] 存放區的 SQL Server 資料庫和 Lync Server 2013 的用途必須位於執行 SQL Server 之伺服器的標準版伺服器 collocated 上。</span><span class="sxs-lookup"><span data-stu-id="9047e-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="9047e-116">[監視伺服器] 與 [封存伺服器] 會將獨立伺服器與 SQL Server 資料庫搭配使用。</span><span class="sxs-lookup"><span data-stu-id="9047e-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

