---
title: Lync Server 2013： 附錄 a： 使用 cmdlet 部署 Survivable Branch Appliance
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
ms.openlocfilehash: cb77c4f22122694d928489f7d61beaa9cbae9355
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>附錄 a： 使用 cmdlet 部署 Survivable Branch Appliance Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-07_

本主題說明如何部署 Survivable Branch Appliance 使用 Lync Server 管理命令介面。 請在中央網站執行這項程序。

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>若要從遠端部署 Survivable Branch Appliance

1.  請依照[將分支網站新增至您的拓樸，Lync Server 2013 中](lync-server-2013-add-branch-sites-to-your-topology.md)新增新的分支網站中的程序。

2.  將分支網站加入網域。

3.  將 RTCUniversalSBATechnicians 群組新增至本機 Administrators 群組。

4.  重新啟動伺服器，然後以 RTCUniversalSBATechnicians 群組成員的身分登入。

5.  在 Lync Server 管理命令介面中，輸入下列命令，預留位置取代為您的組織的正確資訊：
    
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

