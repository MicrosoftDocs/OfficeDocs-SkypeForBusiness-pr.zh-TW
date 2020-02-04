---
title: Lync Server 2013：查看個別 SIP trunks 的相關資訊
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
ms.openlocfilehash: f18b65d119b917d5ba48ef3e6805e4f70ea482ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中查看個別 SIP trunks 的相關資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

SIP trunks 是用來連接 Lync Server 2013 與公用交換電話網絡的語音 over IP 電話網絡。 在早期版本的產品中，trunks 是用來將撥出電話從中繼伺服器傳送到 PSTN 閘道，而每個閘道都限制在單一干線中。 因此，PSTN 閘道與 SIP 幹線本質上完全相同。 針對管理員而言，這表示只要查看關聯 PSTN 閘道的相關資訊，就能查看個別 SIP 主幹的相關資訊。

但在 Lync Server 2013 中，現在可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 已不再是相同的。 因此，這表示系統管理員必須使用新的[CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) Cmdlet，才能查看個別 SIP 幹線的相關資訊。

CsTrunk Cmdlet 可以從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端會話執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>若要查看所有 SIP trunks 的相關資訊

  - 下列命令會傳回貴組織中使用的所有 SIP trunks 資訊：
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>若要查看特定 SIP 主幹的資訊

  - 這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊：192.168.0.240：
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>查看指派給某個池之所有 SIP Trunks 的相關資訊

  - 在這個範例中，會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息：
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

