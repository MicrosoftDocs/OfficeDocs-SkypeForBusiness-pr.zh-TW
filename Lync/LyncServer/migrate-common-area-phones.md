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
ms.openlocfilehash: cba32f8aa95b870190280aebd94d51bdbeec0f2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a>移轉公共區域電話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

常見的區域手機是最常位於共用工作區或常見區域（例如大廳、廚房或工廠地面）的 IP 電話。 常見的區域電話不需要連線到電腦，就能提供 Lync Server UC 功能。 將 Lync Server 2010 部署遷移至 Lync Server 2013 之後，您也必須遷移與舊版常見區域手機相關聯的連絡人物件。 使用 Lync Server 管理命令介面，您將會首先檢索與 Lync Server 2010 常見區域手機相關的所有連絡人物件，然後將這些物件移至 Lync Server 2013 池。

**移轉公共區域電話**

1.  從 Lync Server 2013 前端伺服器，開啟 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要確認已將所有連絡人物件移至 Lync Server 2013 池，請從 Lync Server 管理命令介面輸入下列內容：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    確認所有連絡人物件現在都與 Lync Server 2013 池相關聯。

</div>

<span> </span>

</div>

</div>

</div>

