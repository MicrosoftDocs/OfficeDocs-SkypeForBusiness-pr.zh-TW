---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e33642fe4556397f4c3f71d5dfb582e1868a7ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>移轉公共區域電話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。 公共區域電話不需要連線到電腦，以提供 Lync Server UC 功能。 移轉至 Lync Server 2013 的 Lync Server 2010 部署之後, 您必須也將移轉舊版的公共區域電話相關聯的連絡人物件。 使用 Lync Server 管理命令介面您第一次會擷取所有的連絡人物件與 Lync Server 2010 一般區域電話、 相關聯，然後將這些物件移至 Lync Server 2013 集區。

**移轉公共區域電話**

1.  從 Lync Server 2013 前端伺服器，開啟 [Lync Server 管理命令介面]。

2.  從命令列輸入下列命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要確認所有連絡人物件已移至 Lync Server 2013 集區，從 Lync Server 管理命令介面輸入下列命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。

</div>

<span> </span>

</div>

</div>

</div>

