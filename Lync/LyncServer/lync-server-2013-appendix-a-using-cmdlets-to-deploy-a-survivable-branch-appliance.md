---
title: Lync Server 2013：附錄 A：使用 Cmdlet 部署 Survivable Branch 裝置
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
ms.openlocfilehash: e09cd7e0c5cc8bc20f50ba2c2ae5a1d912f949ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531620"
---
# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>附錄 A：在 Lync Server 2013 中使用 Cmdlet 部署 Survivable Branch 裝置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

本主題說明如何使用 Lync Server 管理命令介面來部署 Survivable 分支裝置。 請在中央網站執行這項程序。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>以遠端方式部署 Survivable 分支裝置

1.  遵循在 [Lync Server 2013 新增分支網站至拓撲中](lync-server-2013-add-branch-sites-to-your-topology.md) 的程式，以加入新的分支網站。

2.  將分支網站加入網域。

3.  將 RTCUniversalSBATechnicians 群組新增至本機 Administrators 群組。

4.  重新啟動伺服器，然後以 RTCUniversalSBATechnicians 群組成員的身分登入。

5.  在 Lync Server 管理命令介面中，輸入下列命令，並將預留位置取代為您組織的正確資訊：
    
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

