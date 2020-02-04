---
title: 移轉類比裝置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e809db03cf098bea07f57673ddcbfc019e15f299
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>移轉類比裝置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

Lync Server 提供模擬裝置的支援。 具體說來，支援的類比裝置是類比音訊電話和類比傳真電腦。 您可以設定合格的閘道，以支援 Lync Server 環境中的類比裝置使用。 從 Lync Server 2010 遷移至 Lync Server 2013 之後，您也必須遷移與類比裝置相關聯的連絡人物件。 使用 Lync Server 管理命令介面，先檢索與 Lync Server 2010 類比裝置相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 池。

<div>

## <a name="to-migrate-analog-devices"></a>遷移類比裝置

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列中，輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  確認所有連絡人物件都已移至 Lync Server 2013 池。 在命令列中，輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  確認所有連絡人物件現在都已與 Lync Server 2013 池建立關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

