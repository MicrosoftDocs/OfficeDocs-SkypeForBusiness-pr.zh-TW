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
ms.openlocfilehash: a074da011f02b0a78d0886badc991651bb7d9c91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="985d7-102">在 Lync Server 2013 中設定 SQL Server</span><span class="sxs-lookup"><span data-stu-id="985d7-102">Configure SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="985d7-103">_**主題上次修改日期：** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="985d7-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="985d7-104">針對您部署的每個資料庫，您可以針對您的 Lync Server 2013 部署（可在資料庫伺服器上 collocated 的所有資料庫）使用單一 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="985d7-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="985d7-105">如需資料庫 collocation 的詳細資訊，請參閱可支援性檔中的[Lync server 2013 支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="985d7-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="985d7-106">此外，您必須先安裝並提供每個 SQL Server 實例，才能完成拓撲建立器中設定資料庫的步驟，或使用 Windows PowerShell Cmdlet 手動建立資料庫。</span><span class="sxs-lookup"><span data-stu-id="985d7-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="985d7-107">如需 SQL Server 支援的詳細資訊，請參閱[Lync Server 2013 的硬體設定](lync-server-2013-hardware-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="985d7-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="985d7-108">若要安裝 Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="985d7-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="985d7-109">請參閱 Microsoft SQL Server 2012 檔，網址<https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>為：。</span><span class="sxs-lookup"><span data-stu-id="985d7-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/en-us/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

