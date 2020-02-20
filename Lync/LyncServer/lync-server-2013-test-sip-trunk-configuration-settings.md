---
title: Lync Server 2013： 測試 SIP 主幹組態設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625de6144ca793ef475ec77721f8a76178a87404
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中測試 SIP 主幹組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

SIP 主幹組態設定用於定義中繼伺服器與服務提供者的公用交換電話網路 (PSTN) 閘道、IP 公用交換機 (PBX) 或工作階段邊界控制器 (SBC) 之間的關係和功能。這些設定將指定下列項目：

  - 主幹是否啟用媒體旁路。

  - 傳送即時傳輸控制通訊協定 (RTCP) 封包的情況。

  - 每個主幹是否需要安全即時通訊協定 (SRTP) 加密。

當您安裝 Microsoft Lync Server 2013 時，為您建立的 SIP 主幹組態設定全域集合。 此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。 系統管理員也可以使用測試 Test-cstrunkconfiguration cmdlet 來確認主幹可以轉換為閘道所能處理的數字至使用者所撥打的號碼。

只可以使用 Windows PowerShell 和[測試 Test-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)指令程式測試主幹組態設定。 從 Lync Server 2013 管理命令介面或 Windows PowerShell 的遠端工作階段，可以執行此 cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格文章 「 快速開始:: 管理 Microsoft Lync Server 2010 使用遠端 PowerShell 」 在[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>若要測試 SIP 主幹組態設定

  - 此命令會確認 Redmond 網站的主幹組態設定可以正確地轉換撥打的號碼 4255551212。
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

