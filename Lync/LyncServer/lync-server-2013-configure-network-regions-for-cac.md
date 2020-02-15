---
title: Lync Server 2013： 設定 CAC 網路地區
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
ms.openlocfilehash: acafaca86af1943d2614349ff42f04fa87faddaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>設定 Lync Server 2013 中的 CAC 網路地區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

<div>


> [!IMPORTANT]  
> 如果您已經建立網路地區的 E9-1-1 或媒體旁路，您可以修改現有的網路地區新增使用<STRONG>Set-csnetworkregion</STRONG> cmdlet 的通話許可控制 (CAC) 的特定設定值。 如需如何修改網路地區的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">建立或修改網路地區 Lync Server 2013 中的</A>。



</div>

*網路地區*是網路集線器或骨幹中設定 CAC、 E9-1-1 和媒體旁路使用。 使用下列程序來建立範例網路拓撲中的網路地區對齊 cac 的網路地區。 若要檢視範例網路拓撲，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。

CAC 的範例網路拓撲有三個區域: 「 北美地區 」、 EMEA，以及 APAC。 每個區域都有指定的中央網站。 針對 「 北美地區 」 區域中，指定的中央站台是名為 「 芝加哥。 下列程序顯示如何使用**New-csnetworkregion** cmdlet 來建立北美地區的範例。

<div>


> [!NOTE]  
> 下列程序，Lync Server 管理命令介面用來建立網路地區。 如需使用 Lync Server 控制台建立網路地區的詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">建立或修改網路地區 Lync Server 2013 中的</A>。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>若要建立通話許可控制的網路地區

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  針對您要建立每個區域，執行**New-csnetworkregion** cmdlet。 例如，若要建立北美地區，請執行：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重複步驟 2 以建立網路地區，EMEA 和 APAC。

</div>

</div>

<span> </span>

</div>

</div>

</div>

