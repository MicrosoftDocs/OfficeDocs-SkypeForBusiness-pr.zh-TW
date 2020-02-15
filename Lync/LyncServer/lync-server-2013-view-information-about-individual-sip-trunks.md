---
title: Lync Server 2013： 檢視個別 SIP 主幹的資訊
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
ms.openlocfilehash: 3163bb6298bef570a68f2fcfd7dec66167549b21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>檢視 Lync Server 2013 中的個別 SIP 主幹的相關資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

SIP 主幹用來連線 Lync Server 2013 Voice over IP 電話網路與公用交換電話網路。 在前一個版本的產品，主幹所用來路由傳送從中繼伺服器到 PSTN 閘道的撥出通話和每個閘道限制為單一主幹。 因此，在 PSTN 閘道與 SIP 主幹所基本上是相同。 系統管理員，這意謂著他們可以檢視個別 SIP 主幹的資訊只是檢視關聯的 PSTN 閘道的相關資訊。

在 Lync Server 2013 中，不過，多個主幹可以現在是已指派給單一的 PSTN 閘道;這表示閘道和主幹不再是同一個。 接著，這表示系統管理員必須使用新的[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet 以檢視個別 SIP 主幹的資訊。

可以執行 Get-cstrunk cmdlet，從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>若要檢視所有 SIP 主幹的資訊

  - 下列命令會傳回用於組織中所有 SIP 主幹的資訊：
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>若要檢視特定 SIP 主幹的資訊

  - 此命令會傳回 192.168.0.240 身分識別的 SIP 主幹的資訊：
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>檢視指派給集區的所有 SIP 主幹的資訊

  - 在這個範例中，傳回指派給 atl-cs-001.litwareinc.com 集區的所有 SIP 主幹資訊-atl-cs-001.litwareinc.com:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

