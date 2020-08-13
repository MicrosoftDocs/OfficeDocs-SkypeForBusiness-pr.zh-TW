---
title: Lync Server 2013：設定 SQL Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffbdb38a0195f87633c8a553147a9ddde4c50fa7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="ff9ec-102">在 Lync Server 2013 中設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="ff9ec-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff9ec-103">_**主題上次修改日期：** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="ff9ec-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="ff9ec-104">針對您部署的每個資料庫，您可以針對所有可在資料庫伺服器上組合之 Lync Server 2013 部署的資料庫使用單一的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="ff9ec-105">如需資料庫組合的詳細資訊，請參閱支援檔中的 [支援的 server 組合 In Lync server 2013](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ff9ec-106">此外，必須先安裝和使用每個 SQL Server 實例，然後才能完成拓撲產生器中設定資料庫的步驟，或以 Windows PowerShell Cmdlet 手動建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ff9ec-107">如需 SQL Server 支援的詳細資訊，請參閱 [Lync Server 2013 的硬體安裝](lync-server-2013-hardware-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="ff9ec-108">安裝 Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="ff9ec-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="ff9ec-109">請參閱 Microsoft SQL Server 2012 檔，網址為： <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="ff9ec-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

