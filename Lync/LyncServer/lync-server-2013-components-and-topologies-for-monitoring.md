---
title: Lync Server 2013：用於監控的元件與拓撲
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
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="edc41-102">Lync Server 2013 中用於監控的元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="edc41-102">Components and topologies for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edc41-103">_**主題上次修改日期：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="edc41-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="edc41-104">因為統一資料收集代理程式會自動安裝並在每個前端伺服器上啟用，因此您不需要設定伺服器來充當監視伺服器;每個前端伺服器都已充當監視伺服器。</span><span class="sxs-lookup"><span data-stu-id="edc41-104">Because the unified data collection agents are automatically installed and activated on each Front End server you do not need to configure a server to act as the Monitoring server; each Front End server already functions as a Monitoring server.</span></span> <span data-ttu-id="edc41-105">不過，您必須安裝並設定資料庫，以做為監視資料的後端資料存放區。</span><span class="sxs-lookup"><span data-stu-id="edc41-105">However, you will need to install and configure a database to act as the backend data store for your monitoring data.</span></span> <span data-ttu-id="edc41-106">Microsoft Lync Server 2013 可以使用下列任何一種資料庫做為監視作業的後端存放區：</span><span class="sxs-lookup"><span data-stu-id="edc41-106">Microsoft Lync Server 2013 can use any of the following databases as the backend store for monitoring:</span></span>

  - <span data-ttu-id="edc41-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="edc41-107">Microsoft SQL Server 2008 R2 Enterprise Edition</span></span>

  - <span data-ttu-id="edc41-108">Microsoft SQL Server 2008 R2 標準版</span><span class="sxs-lookup"><span data-stu-id="edc41-108">Microsoft SQL Server 2008 R2 Standard Edition</span></span>

  - <span data-ttu-id="edc41-109">Microsoft SQL Server 2012 企業版</span><span class="sxs-lookup"><span data-stu-id="edc41-109">Microsoft SQL Server 2012 Enterprise Edition</span></span>

  - <span data-ttu-id="edc41-110">Microsoft SQL Server 2012 標準版</span><span class="sxs-lookup"><span data-stu-id="edc41-110">Microsoft SQL Server 2012 Standard Edition</span></span>

<span data-ttu-id="edc41-111">請注意，您必須使用64位版本的這些資料庫;32位版本的 SQL Server 無法用來做為監視的後端存放區。</span><span class="sxs-lookup"><span data-stu-id="edc41-111">Note that you must use the 64-bit editions of these databases; 32-bit versions of SQL Server cannot be used as the backend store for monitoring.</span></span> <span data-ttu-id="edc41-112">同樣地，Lync Server 2013 不支援 SQL Server 2008 的速成版或 SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="edc41-112">Likewise, Lync Server 2013 does not support the Express Editions of SQL Server 2008 or SQL Server 2012.</span></span> <span data-ttu-id="edc41-113">如需 Lync Server 2013 資料庫需求的詳細資訊，請參閱 Lync Server 2013 支援指南中的[Lync server 2013 主題資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="edc41-113">For more information on database requirements for Lync Server 2013 see the topic [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Lync Server 2013 Supportability guide.</span></span>

<span data-ttu-id="edc41-114">請記住，必須先安裝並設定 SQL Server，然後才能部署和設定監視。</span><span class="sxs-lookup"><span data-stu-id="edc41-114">Keep in mind that SQL Server must be installed and configured before you deploy and configure monitoring.</span></span> <span data-ttu-id="edc41-115">不過，您只需要部署 SQL Server 本身，您不需要提前設定監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="edc41-115">However, you only need to deploy SQL Server itself; you do not have to setup the monitoring databases in advance.</span></span> <span data-ttu-id="edc41-116">相反地，當您發佈 Lync Server 拓撲時，系統會自動為您建立這些資料庫。</span><span class="sxs-lookup"><span data-stu-id="edc41-116">Instead, those databases will automatically be created for you when you publish your Lync Server topology.</span></span>

<span data-ttu-id="edc41-117">監視資料可以與其他類型的資料共用 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-117">Monitoring data can share a SQL Server instance with other types of data.</span></span> <span data-ttu-id="edc41-118">通常，通話詳細資料記錄資料庫（LcsCdr）和體驗資料庫品質（QoEMetrics）會共用相同的 SQL 實例;在相同的 SQL 實例與封存資料庫（LcsLog）相同的情況下，通常也是這兩個監視資料庫。</span><span class="sxs-lookup"><span data-stu-id="edc41-118">Typically, the call detail recording database (LcsCdr) and the Quality of Experience database (QoEMetrics) share the same SQL instance; it is also common for the two monitoring databases to be in the same SQL instance as the archiving database (LcsLog).</span></span> <span data-ttu-id="edc41-119">關於 SQL Server 實例唯一的真正需求是，任何一個 SQL Server 實例都僅限於下列專案：</span><span class="sxs-lookup"><span data-stu-id="edc41-119">About the only real requirement with SQL Server instances is that any one instance of SQL Server is limited to the following:</span></span>

  - <span data-ttu-id="edc41-120">Lync Server 2013 後端資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-120">One instance of the Lync Server 2013 backend database.</span></span> <span data-ttu-id="edc41-121">（作為一般規則，建議您不要在相同的 SQL 實例（甚至是同一台電腦）上 collocated 您的監視資料庫，就像是後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="edc41-121">(As a general rule, it is not recommended that your monitoring database be collocated in the same SQL instance, or even on the same computer, as the backend database.</span></span> <span data-ttu-id="edc41-122">雖然技術上有可能，您可以使用後端資料庫所需的磁碟空間來執行監視資料庫的風險。</span><span class="sxs-lookup"><span data-stu-id="edc41-122">Although technically possible, you run the risk of the monitoring database using up disk space needed by the backend database.)</span></span>

  - <span data-ttu-id="edc41-123">[通話詳細資料記錄] 資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-123">One instance of the call detail recording database.</span></span>

  - <span data-ttu-id="edc41-124">體驗資料庫品質的一個實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-124">One instance of the Quality of Experience database.</span></span>

  - <span data-ttu-id="edc41-125">存檔資料庫的一個實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-125">One instance of the archiving database.</span></span>

<span data-ttu-id="edc41-126">換句話說，在同一個 SQL Server 實例中，您無法使用 LcsCdr 資料庫的兩個實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-126">In other words, you cannot have two instances of the LcsCdr database in the same instance of SQL Server.</span></span> <span data-ttu-id="edc41-127">如果您需要 LcsCdr 資料庫的多個實例，您就需要設定多個 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="edc41-127">If you need multiple instances of the LcsCdr database then you will need to configure multiple instances of SQL Server.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="edc41-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="edc41-128">See Also</span></span>


[<span data-ttu-id="edc41-129">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="edc41-129">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

