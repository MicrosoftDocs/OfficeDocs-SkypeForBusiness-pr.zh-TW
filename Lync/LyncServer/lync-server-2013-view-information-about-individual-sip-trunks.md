---
title: Lync Server 2013：查看個別 SIP 主幹的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d01a56ca0365c041ae9469dee2d328f81acd3e65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523580"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中查看個別 SIP 主幹的相關資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

SIP 主幹是用於連接 Lync Server 2013 Voice over IP phone 網路與公用交換電話網路。 在舊版本的產品中，主幹是用來將撥出電話從轉送伺服器路由傳送至 PSTN 閘道，而每個閘道都限制為單一主幹。 因此，PSTN 閘道和 SIP 主幹本質上都相同。 針對系統管理員而言，只要查看相關聯的 PSTN 閘道的相關資訊，就可以查看個別 SIP 主幹的相關資訊。

不過，在 Lync Server 2013 中，現在可以將多個主幹指派給單一 PSTN 閘道;這表示閘道和主幹不再是一個，也是相同的。 反過來，這表示系統管理員必須使用新的 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet，才能查看個別 SIP 主幹的相關資訊。

Get-CsTrunk Cmdlet 既可以從 Lync Server 2013 管理命令介面，也可以從 Windows PowerShell 的遠端會話執行。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>若要查看所有 SIP 主幹的資訊

  - 下列命令會傳回組織中使用之所有 SIP 主幹的資訊：
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>若要查看特定 SIP 主幹的資訊

  - 這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看指派至集區之所有 SIP 主幹的資訊

  - 在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

