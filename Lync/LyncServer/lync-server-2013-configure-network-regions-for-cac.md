---
title: Lync Server 2013：為 CAC 設定網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中設定 CAC 的網路區域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

<div>


> [!IMPORTANT]  
> 如果您已為 E9 （1-1 或媒體旁路）建立網路區域，您可以使用<STRONG>CsNetworkRegion</STRONG> Cmdlet 新增撥號許可控制（CAC）專用的設定來修改現有的網路區域。 如需如何修改網路區域的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中建立或修改網路區域</A>。



</div>

*網路區域*是用來設定 CAC、E9-1 及媒體旁路的網路中心或 backbones。 使用下列程式建立網路區域，以在 CAC 的範例網路拓撲中與網路區域對齊。 若要查看範例網路拓撲，請參閱在規劃檔中[收集 Lync Server 2013 的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

CAC 的範例網路拓朴有三個區域：北美、EMEA 及 APAC。 每個地區都有指定的中心網站。 對北美地區而言，指定的中央網站是名為芝加哥。 下列程式示範如何使用**新的 CsNetworkRegion** Cmdlet 來建立北美區域的範例。

<div>


> [!NOTE]  
> 在下列程式中，Lync Server 管理命令介面是用來建立網路區域。 如需使用 Lync Server [控制台] 建立網路區域的詳細資料，請參閱<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中建立或修改網路區域</A>。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>為通話許可控制建立網路區域

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  針對您需要建立的每個區域，執行**新的 CsNetworkRegion** Cmdlet。 例如，若要建立北美地區，請執行：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重複步驟2，建立網路地區、EMEA 及 APAC。

</div>

</div>

<span> </span>

</div>

</div>

</div>

