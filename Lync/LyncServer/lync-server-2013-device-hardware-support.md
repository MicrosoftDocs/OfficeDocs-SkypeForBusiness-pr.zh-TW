---
title: Lync Server 2013 裝置硬體支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Lync Server 2013 中的裝置硬體支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

在部署 IP 電話和類比裝置之前，必須先進行特定的硬體設定。

執行 Lync 手機版的 IP 電話支援連結層探索通訊協定-媒體端點探索（LLDP-MED-V）和乙太網上電（PoE）。若要充分利用 LLDP-MED-V，交換器必須支援 IEEE 802.1 AB 和 ANSI/TIA-1057。 若要充分利用 PoE，交換器必須支援 PoE 802.3 AF 或 802.3 at。

若要啟用 LLDP，系統管理員必須使用 [切換主控台] 視窗來啟用 LLDP，並使用正確的語音 VLAN 識別碼設定 LLDP-MED-V 網路原則。

此外，如果您的部署包含類比裝置，您必須將模擬閘道設定為使用 Lync Server，且閘道必須是下列其中一項：

  - 類比電話配接器（ATA）

  - PSTN 類比閘道

  - 包含 PSTN 模擬閘道的 Survivable 分支裝置

  - Survivable 分支裝置，其中包含可與 ATA 通訊的 PSTN 閘道

若要瞭解如何設定類比閘道，請參閱 Lync Server 2010 TechNet 文件庫[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)中的「規劃以部署類比裝置」。 （類比裝置在 lync server 2013 中的運作方式與在 Lync Server 2010 中一樣。）

<div>


> [!IMPORTANT]  
> 如果交換器支援此功能，您可以將開關設定為增強9-1-1 （E9-1-1）。



</div>

</div>

<span> </span>

</div>

</div>

</div>

