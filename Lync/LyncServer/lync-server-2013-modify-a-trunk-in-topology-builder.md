---
title: Lync Server 2013：在拓撲產生器中修改主幹
description: Lync Server 2013：在拓撲產生器中修改主幹。
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
ms.openlocfilehash: 5f453997664dbe3048a7aa915732b4d95a932dd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550479"
---
# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 中的拓撲產生器中修改主幹

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

請依照下列步驟，修改主幹的替代媒體 IP 位址和替代旁路識別碼。

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a>修改主幹的替代媒體 IP 位址

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsPstnGateway Cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a>修改主幹的替代 BypassID

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 Set-CsPstnGateway Cmdlet，並修改 Lync Server 管理命令介面中的 [AlternateBypassId] 欄位。
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

