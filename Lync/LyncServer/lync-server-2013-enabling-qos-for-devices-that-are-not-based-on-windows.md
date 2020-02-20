---
title: Lync Server 2013： 不採用 Windows 的裝置啟用 QoS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad830b2cf15e3f34c443feaa5ea21e19279804cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>不採用 Windows 的裝置啟用 QoS Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

當您安裝 Microsoft Lync Server 2013 時，服務品質 (QoS) 將未啟用用於貴組織中使用非 Windows 作業系統的任何裝置。 您可以執行從 Lync Server 2013 管理命令介面中的下列命令來確認：

    Get-CsMediaConfiguration

假設您已對媒體組態設定執行變更，就應該會得到類似下列的資訊：

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

如果 EnableQoS 屬性設為 False （如上述輸出） 表示 Quality of Service 未啟用電腦和使用非 Windows 作業系統的裝置。 Lync Phone Edition 裝置; 用預設會啟用 QoS不過，很可能停用 Lync Phone Edition 的服務品質。

若要啟用的服務品質在全域範圍，執行從 Lync Server 管理命令介面中的下列命令：

    Set-CsMediaConfiguration -EnableQoS $True

先前的命令會啟用全域範圍的 QoS；但需要注意的是，媒體組態設定也會套用至網站範圍。若您要為網站啟用服務品質，就必須在呼叫 Set-CsMediaConfiguration 時包含組態設定的識別。例如，此命令會啟用 Redmond 網站的 QoS：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> 您是否需要啟用網站範圍的 QoS？答案是不一定。指派至網站範圍的設定會優先於指派至全域範圍的設定。假設您已啟用全域範圍的 QoS，但停用網站範圍的 QoS (針對 Redmond 網站)。則在此情況中，會因為網站設定優先，而停用 Redmond 網站的服務品質。若要啟用 Redmond 網站的 QoS，就必須使用會套用至網站的媒體組態設定。



</div>

如果您想要同時啟用 [再執行此命令在 Lync Server 管理命令介面中的所有媒體組態設定 （不論範圍為何） QoS:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

您可以停 QoS 的裝置，使用非 Windows 作業系統 EnableQoS 屬性的值設為 False。 例如：

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

這使您能夠在網路的某些部分停用服務品質的同時，於網路的其他部分啟用 QoS (例如在 Redmond 網站上)。

僅可啟用 QoS 和已停用使用 Windows PowerShell 這些選項中沒有提供 Lync Server Control Panel。

</div>

<span> </span>

</div>

</div>

</div>

