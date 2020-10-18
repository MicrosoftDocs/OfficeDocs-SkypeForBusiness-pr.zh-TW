---
title: Lync Server 2013：設定 CAC 的網路地區
description: Lync Server 2013：設定 CAC 的網路地區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577559"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中設定 CAC 的網路地區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

<div>


> [!IMPORTANT]  
> 如果您已建立 E9-1-1 或媒體旁路的網路地區，您可以使用 <STRONG>Set-CsNetworkRegion</STRONG> 指令程式 (CAC) 新增通話許可控制的特定設定，以修改現有的網路地區。 如需如何修改網路地區的範例，請參閱 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中建立或修改網路地區</A>。



</div>

*網路地區* 是網路中樞或骨幹，用來設定 CAC、E9-1-1 和媒體旁路。 請使用下列程式建立網路地區，以與 CAC 的範例網路拓撲中的網路地區對齊。 若要查看範例網路拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

CAC 的範例網路拓撲有三個區域：北美、EMEA 和 APAC。 每個地區都有指定的中央網站。 在北美地區，指定的中央網站命名為芝加哥。 下列程式顯示如何使用 **New-CsNetworkRegion** Cmdlet 來建立北美地區的範例。

<div>


> [!NOTE]  
> 在下列程式中，Lync Server 管理命令介面是用來建立網路地區。 如需使用 Lync Server 控制台建立網路地區的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中建立或修改網路地區</A>。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>為通話許可控制建立網路地區

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  針對您需要建立的每個地區，執行 **New-CsNetworkRegion** Cmdlet。 例如，若要建立北美地區，請執行：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重複步驟2以建立網路地區（EMEA 和 APAC）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

