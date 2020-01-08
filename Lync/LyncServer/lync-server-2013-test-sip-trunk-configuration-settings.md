---
title: Lync Server 2013：測試 SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a6b1c8a43258c849de73b10a10bccf8ff537c5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中測試 SIP 幹線配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。 這些設定會以指定的方式執行以下操作：

  - 是否應該在 trunks 上啟用媒體旁路。

  - 傳送即時傳輸控制通訊協定（RTCP）資料包的條件。

  - 每個幹線是否都需要安全的即時通訊協定（SRTP）加密。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。 此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。 系統管理員也可以使用 New-cstrunkconfiguration Cmdlet 來驗證主幹能將使用者撥出的號碼轉換成可由閘道處理的數位。

只能使用 Windows PowerShell 和[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) Cmdlet 來測試幹線設定設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>測試 SIP 幹線設定設定

  - 這個命令會驗證雷德蒙網站的幹線設定設定可以正確地轉換撥打的號碼4255551212。
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

