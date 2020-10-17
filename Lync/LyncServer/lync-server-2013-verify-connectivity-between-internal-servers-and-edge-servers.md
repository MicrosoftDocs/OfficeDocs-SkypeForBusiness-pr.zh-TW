---
title: 驗證內部伺服器和 Edge Server 之間的連線能力
description: 驗證內部伺服器和 Edge Server 之間的連線能力。
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
ms.openlocfilehash: f86f87428d7eaf91b8f70422cfee712584252fad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547129"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="8fae4-103">驗證 Lync Server 2013 中內部伺服器和 Edge Server 之間的連線能力</span><span class="sxs-lookup"><span data-stu-id="8fae4-103">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fae4-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8fae4-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8fae4-105">在 Lync Server 2013 中，可使用個別驗證嚮導，以協助驗證 Edge Server 與內部伺服器之間的連線能力。</span><span class="sxs-lookup"><span data-stu-id="8fae4-105">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="8fae4-106">在 [Lync Server 2013] 中，當您安裝 Edge Server 時，會自動進行連線驗證。</span><span class="sxs-lookup"><span data-stu-id="8fae4-106">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="8fae4-107">您可以在中央管理存放區 (所在的內部電腦上執行 Windows PowerShell **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證設定資訊的複寫，也可以在已安裝任何已加入網域的電腦上，執行 ( # A0) 之 Lync Server 2013 核心元件的任何已加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="8fae4-107">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="8fae4-108">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="8fae4-108">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="8fae4-109">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet、等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。</span><span class="sxs-lookup"><span data-stu-id="8fae4-109">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="8fae4-110">您可以單獨驗證外部使用者連線，包括使用 Office Communications Server 遠端連線分析程式來驗證遠端使用者連線。</span><span class="sxs-lookup"><span data-stu-id="8fae4-110">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="8fae4-111">如需詳細資訊，請參閱 [在 Lync Server 2013 中驗證外部使用者的連線能力](lync-server-2013-verify-connectivity-for-external-users.md)。</span><span class="sxs-lookup"><span data-stu-id="8fae4-111">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

