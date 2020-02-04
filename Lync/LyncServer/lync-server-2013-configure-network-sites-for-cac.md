---
title: Lync Server 2013：針對 CAC 設定網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0958c74d6f1ce587886b7a8456aee44381c00ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中設定 CAC 的網路網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> 如果您已為 E9 （1-1 或媒體旁路）建立網路網站，您可以使用<STRONG>CsNetworkSite</STRONG> Cmdlet 來修改現有的網路網站，以套用頻寬原則設定檔。 如需如何修改網路網站的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中建立或修改網路網站</A>。



</div>

*Network sites*是呼叫許可控制（CAC）、E9-1 及媒體旁路部署的每個網路區域內的辦公室或位置。 使用下列程式來建立網路網站，以在 CAC 的範例網路拓撲中與網路網站對齊。 這些程式示範如何建立和設定受 WAN 頻寬限制的網路網站，因此需要頻寬原則來限制即時音訊或視頻流量流程。

在範例 CAC 部署中，北美地區有六個網站。 這些網站中有三個是受 WAN 頻寬的限制： Reno、Albuquerque 及。 *不*受 WAN 頻寬限制的其他三個網站：北京、芝加哥及底特律。 如需如何建立或修改其他網路網站的範例，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)。

若要查看範例網路拓撲，請參閱在規劃檔中[收集 Lync Server 2013 的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div class=" ">


> [!NOTE]  
> 在下列程式中，Lync Server 管理命令介面是用來建立網路網站。 如需使用 Lync Server [控制台] 建立網路網站的詳細資料，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中建立或修改網路網站</A>。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>建立通話許可控制的網路網站

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行**新的 CsNetworkSite** Cmdlet 來建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。 例如，執行：
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  若要為整個範例拓撲完成建立網路網站，請針對 EMEA 與 APAC 區域中的頻寬限制網路網站，重複步驟2。

</div>

</div>

<span> </span>

</div>

</div>

</div>

