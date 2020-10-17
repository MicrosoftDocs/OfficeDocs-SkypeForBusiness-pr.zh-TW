---
title: 移轉類比裝置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb0f29f9a217676829ff3869fcda3759359944b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503610"
---
# <a name="migrate-analog-devices"></a>移轉類比裝置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-16_

Lync Server 提供類比裝置的支援。 具體而言，支援的類比裝置為類比語音電話與類比傳真機。 您可以設定合格的閘道，以支援在 Lync Server 環境中使用類比裝置。 從 Lync Server 2010 遷移至 Lync Server 2013 之後，您也必須遷移與類比裝置相關聯的連絡人物件。 使用 Lync Server 管理命令介面，先找回 Lync Server 2010 類比裝置相關聯的所有連絡人物件，然後將這些物件移至 Lync Server 2013 集區。

<div>

## <a name="to-migrate-analog-devices"></a>遷移類比裝置

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  在命令列中輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  確認已將所有連絡人物件移至 Lync Server 2013 集區。 在命令列中輸入：
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  確認所有連絡人物件現在已與 Lync Server 2013 集區相關聯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

