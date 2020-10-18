---
title: Lync Server 2013：監控的元件與拓撲
description: Lync Server 2013：監控的元件與拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8767a7eb16ca85e9606838606a6e86ee1296fc0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576839"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="352d8-103">Lync Server 2013 中監控的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="352d8-103">Components and topologies for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="352d8-104">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="352d8-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="352d8-105">由於整合資料集合代理程式會在每一部前端伺服器上自動安裝及啟用，因此您不需要將伺服器設定為監視伺服器;每一部前端伺服器都已做為監控伺服器的功能。</span><span class="sxs-lookup"><span data-stu-id="352d8-105">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="352d8-106">不過，您必須安裝並設定資料庫，以充當監控資料的後端資料儲存區。</span><span class="sxs-lookup"><span data-stu-id="352d8-106">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="352d8-107">Microsoft Lync Server 2013 可使用下列任何資料庫做為監視的後端存放區：</span><span class="sxs-lookup"><span data-stu-id="352d8-107">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="352d8-108">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="352d8-108">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="352d8-109">Microsoft SQL Server 2008 R2 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="352d8-109">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="352d8-110">Microsoft SQL Server 2012 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="352d8-110">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="352d8-111">Microsoft SQL Server 2012 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="352d8-111">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="352d8-112">請注意，您必須使用這些資料庫的64位版本;32位版本的 SQL Server 無法用作監視的後端存放區。</span><span class="sxs-lookup"><span data-stu-id="352d8-112">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="352d8-113">同樣地，Lync Server 2013 不支援 SQL Server 2008 的速成版或 SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="352d8-113">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="352d8-114">如需 Lync Server 2013 資料庫需求的詳細資訊，請參閱 Lync Server 2013 支援指南中的主題 [資料庫軟體支援（Lync server 2013](lync-server-2013-database-software-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="352d8-114">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="352d8-115">請記住，必須先安裝及設定 SQL Server，才能部署及設定監視。</span><span class="sxs-lookup"><span data-stu-id="352d8-115">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="352d8-116">不過，您只需要部署 SQL Server 本身;您不需要事先設定監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="352d8-116">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="352d8-117">相反地，當您發佈 Lync Server 拓撲時，會自動為您建立這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="352d8-117">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="352d8-118">監視資料可以與其他類型的資料共用 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-118">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="352d8-119">一般來說，詳細通話記錄資料庫 (LcsCdr) 和經驗品質資料庫 (QoEMetrics) 共用相同的 SQL 實例;這兩個監視資料庫也一般都位於與封存資料庫 (LcsLog) 相同的 SQL 實例中。</span><span class="sxs-lookup"><span data-stu-id="352d8-119">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="352d8-120">關於 SQL Server 實例的唯一實際需求是，任何一個 SQL Server 實例都限制為下列各項：</span><span class="sxs-lookup"><span data-stu-id="352d8-120">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="352d8-121">Lync Server 2013 後端資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-121">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="352d8-122"> (一般規則，不建議您在相同的 SQL 實例（甚至是在相同的電腦上），將監控資料庫組合至後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="352d8-122">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="352d8-123">您可以使用後端資料庫所需的磁碟空間來執行監控資料庫的風險，但從技術上講可行。 ) </span><span class="sxs-lookup"><span data-stu-id="352d8-123">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="352d8-124">通話詳細資料記錄資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-124">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="352d8-125">經驗品質資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-125">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="352d8-126">封存資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-126">One instance of the archiving database.</span></span>

<span data-ttu-id="352d8-127">換句話說，在相同的 SQL Server 實例中，您不能有兩個 LcsCdr 資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-127">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="352d8-128">如果您需要 LcsCdr 資料庫的多個實例，則需要設定多個 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="352d8-128">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="352d8-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="352d8-129">See Also</span></span>


[<span data-ttu-id="352d8-130">在 Lync Server 2013 中部署監控</span><span class="sxs-lookup"><span data-stu-id="352d8-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

