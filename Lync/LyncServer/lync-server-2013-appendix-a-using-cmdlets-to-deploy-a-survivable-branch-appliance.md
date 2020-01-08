---
title: Lync Server 2013：附錄 A：使用 Cmdlet 部署 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9541e6cb63cee91a6bfd1072695fb3ce09a0134
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Lync Server 2013 中的附錄 A：使用 Cmdlet 部署 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-07_

本主題說明如何使用 Lync Server 管理命令介面部署 Survivable 分支裝置。 在中央網站執行此程式。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>遠端部署 Survivable 分支裝置

1.  請依照在[Lync Server 2013 中新增分支網站至拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)中的程式，新增分支網站。

2.  將分支網站加入網域。

3.  將 [RTCUniversalSBATechnicians] 群組新增至 [本機管理員] 群組。

4.  重新開機伺服器，並以 RTCUniversalSBATechnicians 群組成員的身分登入。

5.  在 Lync Server 管理命令介面中，輸入下列命令，並將預留位置替換為貴組織的正確資訊：
    
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

