---
title: 移轉公共區域電話
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af08e6de9b832289e898fd27003b896dd40fa81c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503570"
---
# <a name="migrate-common-area-phones"></a>移轉公共區域電話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

公共區域電話為最常在共用工作區或公共區域 (例如大廳、廚房或工廠) 的 IP 電話。 一般區域電話不需要連線到電腦，就能提供 Lync Server UC 功能。 將 Lync Server 2010 部署遷移至 Lync Server 2013 之後，您還必須遷移與舊版通用區域電話相關聯的連絡人物件。 使用 Lync Server 管理命令介面您會先取得與 Lync Server 2010 通用區域電話相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。

**移轉公共區域電話**

1.  在 Lync Server 2013 前端伺服器上，開啟 [Lync Server 管理命令介面]。

2.  從命令列輸入下列命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要確認已將所有連絡人物件移至 Lync Server 2013 集區，請從 Lync Server 管理命令介面輸入下列命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。

</div>

<span> </span>

</div>

</div>

</div>

