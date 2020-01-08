---
title: Lync Server 2013：設定用於存檔的系統平臺
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="12c91-102">在 Lync Server 2013 中設定存檔的系統平臺</span><span class="sxs-lookup"><span data-stu-id="12c91-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12c91-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="12c91-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="12c91-104">開始部署封存前，您必須在符合系統需求的硬體上安裝所需的作業系統及任何其他必備軟體：</span><span class="sxs-lookup"><span data-stu-id="12c91-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="12c91-105">**Lync server 2013 platform**   lync server 2013 部署沒有存檔伺服器。</span><span class="sxs-lookup"><span data-stu-id="12c91-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="12c91-106">相反地，整合的資料收集代理程式會在前端伺服器和標準版伺服器上執行，以捕獲資料以進行封存，因此不需要個別的系統平臺即可託管封存。</span><span class="sxs-lookup"><span data-stu-id="12c91-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="12c91-107">**資料儲存平臺**   在 Lync Server 2013 中，您可以使用下列其中一種方法來儲存資料：</span><span class="sxs-lookup"><span data-stu-id="12c91-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="12c91-108">**Microsoft Exchange 整合**   如果您想要使用 Exchange 2013 部署來儲存 Lync Server 2013 存檔資料，而不是或除了針對儲存在歸檔資料的另一個資料庫之外，您的 exchange 部署必須執行 exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="12c91-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="12c91-109">如需設定 Exchange 2013 的系統平臺的詳細資料，請參閱 Exchange 產品檔。</span><span class="sxs-lookup"><span data-stu-id="12c91-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="12c91-110">**SQL server**   如果您想要使用個別的 sql server 資料庫儲存歸檔資料，而不是使用 Microsoft Exchange 整合，您必須先設定資料庫的系統平臺，然後再部署歸檔。</span><span class="sxs-lookup"><span data-stu-id="12c91-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="12c91-111">特定的系統平臺需求取決於您是否使用 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 進行歸檔資料庫。</span><span class="sxs-lookup"><span data-stu-id="12c91-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="12c91-112">如需針對這些資料庫設定系統平臺的詳細資料，請參閱 Microsoft SQL Server 2008 R2 和 Microsoft SQL Server 2012 產品檔。</span><span class="sxs-lookup"><span data-stu-id="12c91-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="12c91-113">**檔案伺服器平臺**   Lync server 2013 會將 Lync server 存檔檔案儲存在您設定前端伺服器或標準版伺服器時，您針對檔案儲存區所指定的相同位置。</span><span class="sxs-lookup"><span data-stu-id="12c91-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="12c91-114">您不能指定單獨的位置來儲存檔案儲存空間，因此不需要個別的系統平臺就能儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="12c91-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="12c91-115">如果您使用 Microsoft Exchange 整合，Exchange 2013 將檔案儲存在 exchange 2013 伺服器上，以供駐留在這些 Exchange 伺服器上的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="12c91-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

