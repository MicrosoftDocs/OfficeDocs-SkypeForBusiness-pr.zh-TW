---
title: Lync Server 2013： 修改在拓撲產生器的主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936de680a13a3f9ec851181876ce7a80c1784e52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a>修改主幹在 Lync Server 2013 中的拓撲產生器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

請依照下列步驟，修改主幹的替代媒體 IP 位址和替代旁路識別碼。

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a>修改主幹的替代媒體 IP 位址

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行 Set-cspstngateway cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a>修改主幹的替代 BypassID

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行 Set-cspstngateway cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

