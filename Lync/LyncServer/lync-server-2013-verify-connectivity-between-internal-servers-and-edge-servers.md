---
title: 驗證內部伺服器和 Edge Server 之間的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27ca4874ac8c991828383afb524be1a1868bb7e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="19e06-102">在 Lync Server 2013 中驗證內部伺服器和 Edge Server 之間的連線</span><span class="sxs-lookup"><span data-stu-id="19e06-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19e06-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="19e06-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="19e06-104">在 Lync Server 2013 中，有一個單獨的驗證嚮導可用來協助驗證邊緣伺服器與內部伺服器之間的連線性。</span><span class="sxs-lookup"><span data-stu-id="19e06-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="19e06-105">在 Lync Server 2013 中，連線驗證是在您安裝 Edge 伺服器時自動完成。</span><span class="sxs-lookup"><span data-stu-id="19e06-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="19e06-106">您可以在中央管理儲存所在的內部電腦（或已加入任何已安裝 Lync Server 2013 核心元件（OcsCore .msi）的電腦上，執行 Windows PowerShell **CsManagementStoreReplicationStatus** Cmdlet，以驗證將配置資訊複製到 edge。</span><span class="sxs-lookup"><span data-stu-id="19e06-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="19e06-107">初始結果可能會指出狀態為「False」，而不是「True」以進行複製。</span><span class="sxs-lookup"><span data-stu-id="19e06-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="19e06-108">如果是，請執行**CsManagementStoreReplication** Cmdlet，並允許複製完成時間，然後再次執行**CsManagementStoreReplicationStatus** 。</span><span class="sxs-lookup"><span data-stu-id="19e06-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="19e06-109">您可以分別驗證外部使用者連線，包括使用 Office 通訊伺服器遠端連線分析程式來驗證遠端使用者的連線性。</span><span class="sxs-lookup"><span data-stu-id="19e06-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="19e06-110">如需詳細資訊，請參閱[在 Lync Server 2013 中驗證外部使用者的連線能力](lync-server-2013-verify-connectivity-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="19e06-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

