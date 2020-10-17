---
title: Lync Server 2013：設定系統平臺進行封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac0a0e39a65b32b42398aab832e7010573534807
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497550"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="3a565-102">在 Lync Server 2013 中設定用以封存的系統平臺</span><span class="sxs-lookup"><span data-stu-id="3a565-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a565-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3a565-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3a565-104">開始部署封裝之前，必須先在符合系統需求的硬體上安裝所需作業系統，以及所有先決條件軟體。</span><span class="sxs-lookup"><span data-stu-id="3a565-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="3a565-105">**Lync Server 2013 平臺**    Lync Server 2013 部署沒有封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="3a565-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="3a565-106">但在前端伺服器及 Standard Edition Server 上執行的整合資料收集代理程式會擷取封裝的資料，因此不需要使用另一個系統平台主控封裝。</span><span class="sxs-lookup"><span data-stu-id="3a565-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="3a565-107">**資料儲存平臺**    在 Lync Server 2013 中，您可以使用下列任一項儲存資料：</span><span class="sxs-lookup"><span data-stu-id="3a565-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="3a565-108">**Microsoft Exchange 整合**    如果您想要使用 Exchange 2013 部署來儲存 Lync Server 2013 封存資料，而不是除了設定個別資料庫來儲存封存資料，您的 Exchange 部署必須執行 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="3a565-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="3a565-109">如需有關為 Exchange 2013 設定系統平臺的詳細資訊，請參閱 Exchange 產品的檔。</span><span class="sxs-lookup"><span data-stu-id="3a565-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="3a565-110">**SQL Server**    如果您想要使用個別的 SQL Server 資料庫來儲存封存資料，而不是使用 Microsoft Exchange 整合，您必須在部署封存之前，先設定資料庫的系統平臺。</span><span class="sxs-lookup"><span data-stu-id="3a565-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="3a565-111">特定的系統平臺需求取決於您針對封存資料庫使用的是 Microsoft SQL Server 2008 R2 還是 Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="3a565-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="3a565-112">如需設定這些資料庫之系統平臺的詳細資訊，請參閱 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 產品檔。</span><span class="sxs-lookup"><span data-stu-id="3a565-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="3a565-113">**檔案伺服器平臺**    當您設定前端伺服器或 Standard Edition server 時，lync Server 2013 會將 Lync Server 封存檔案儲存在您為檔存放區指定的相同位置。</span><span class="sxs-lookup"><span data-stu-id="3a565-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="3a565-114">您無法指定另一個封裝檔案儲存的位置，所以也不需要另一個封裝檔案儲存的系統平台。</span><span class="sxs-lookup"><span data-stu-id="3a565-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="3a565-115">如果您使用 Microsoft Exchange 整合，Exchange 2013 檔案中封存的 Lync 通訊儲存在 Exchange 2013 伺服器上，供位於這些 Exchange 伺服器的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="3a565-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

