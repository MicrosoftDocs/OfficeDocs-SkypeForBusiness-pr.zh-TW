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
ms.openlocfilehash: 0bc1c3420c22f4cc58bd0e617fd9ba98e16102c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a>移轉類比裝置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10-16_

Lync Server 的類比裝置提供支援。 具體而言，支援的類比裝置為類比語音電話與類比傳真機。 您可以設定 Lync Server 環境中支援的類比裝置使用完整的閘道。 從 Lync Server 2010 移轉至 Lync Server 2013 之後，您也必須移轉相關聯的類比裝置連絡人物件。 使用 Lync Server 管理命令介面來第一次擷取與 Lync Server 2010 類比裝置，相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。

<div>

## <a name="to-migrate-analog-devices"></a>移轉類比裝置

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  在命令列中輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  確認所有連絡人物件已被移至 Lync Server 2013 集區。 在命令列中輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

