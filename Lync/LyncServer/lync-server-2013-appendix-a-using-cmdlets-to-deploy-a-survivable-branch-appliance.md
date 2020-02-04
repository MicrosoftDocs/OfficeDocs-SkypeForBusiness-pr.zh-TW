---
title: Lync Server 2013：附錄 A：使用 Cmdlet 部署 Survivable Branch Appliance
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
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="526a7-102">Lync Server 2013 中的附錄 A：使用 Cmdlet 部署 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="526a7-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526a7-103">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="526a7-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="526a7-104">本主題說明如何使用 Lync Server 管理命令介面部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="526a7-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="526a7-105">在中央網站執行此程式。</span><span class="sxs-lookup"><span data-stu-id="526a7-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="526a7-106">遠端部署 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="526a7-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="526a7-107">請依照在[Lync Server 2013 中新增分支網站至拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)中的程式，新增分支網站。</span><span class="sxs-lookup"><span data-stu-id="526a7-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="526a7-108">將分支網站加入網域。</span><span class="sxs-lookup"><span data-stu-id="526a7-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="526a7-109">將 [RTCUniversalSBATechnicians] 群組新增至 [本機管理員] 群組。</span><span class="sxs-lookup"><span data-stu-id="526a7-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="526a7-110">重新開機伺服器，並以 RTCUniversalSBATechnicians 群組成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="526a7-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="526a7-111">在 Lync Server 管理命令介面中，輸入下列命令，並將預留位置替換為貴組織的正確資訊：</span><span class="sxs-lookup"><span data-stu-id="526a7-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
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

