---
title: Lync Server 2013：附錄 A：使用 Cmdlet 部署 Survivable Branch 裝置
description: Lync Server 2013：附錄 A：使用 Cmdlet 部署 Survivable Branch 裝置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bf1fe5d86900ec5da95ed9020720149a5015f19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561869"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="16d57-103">附錄 A：在 Lync Server 2013 中使用 Cmdlet 部署 Survivable Branch 裝置</span><span class="sxs-lookup"><span data-stu-id="16d57-103">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d57-104">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="16d57-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="16d57-105">本主題說明如何使用 Lync Server 管理命令介面來部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="16d57-105">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="16d57-106">請在中央網站執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="16d57-106">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="16d57-107">以遠端方式部署 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="16d57-107">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="16d57-108">遵循在 [Lync Server 2013 新增分支網站至拓撲中](lync-server-2013-add-branch-sites-to-your-topology.md) 的程式，以加入新的分支網站。</span><span class="sxs-lookup"><span data-stu-id="16d57-108">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="16d57-109">將分支網站加入網域。</span><span class="sxs-lookup"><span data-stu-id="16d57-109">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="16d57-110">將 RTCUniversalSBATechnicians 群組新增至本機 Administrators 群組。</span><span class="sxs-lookup"><span data-stu-id="16d57-110">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="16d57-111">重新啟動伺服器，然後以 RTCUniversalSBATechnicians 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="16d57-111">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="16d57-112">在 Lync Server 管理命令介面中，輸入下列命令，並將預留位置取代為您組織的正確資訊：</span><span class="sxs-lookup"><span data-stu-id="16d57-112">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

