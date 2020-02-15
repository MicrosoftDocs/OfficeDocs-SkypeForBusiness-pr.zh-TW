---
title: Lync Server 2013： 設定 CAC 的網路網站
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
ms.openlocfilehash: f449d26515c6790ec8582676ca57ed897f12dc40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>設定 Lync Server 2013 中的 CAC 的網路網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-05_

<div class=" ">


> [!IMPORTANT]  
> 如果您已經建立網路網站的 E9-1-1 或媒體旁路，您可以修改現有的網路網站，以使用<STRONG>Set-csnetworksite</STRONG> cmdlet 來套用頻寬原則設定檔。 如需如何修改網路網站的範例，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">建立或修改 Lync Server 2013 中的網路網站</A>。



</div>

*網路站台*是辦公室或位置內的每個網路地區通話許可控制 (CAC)、 E9-1-1 和媒體旁路的部署。 使用下列程序來建立對齊 CAC 的範例網路拓撲中的網路網站的網站。 這些程序顯示如何建立並設定受到 WAN 頻寬限制的網路網站，並因此需要限制即時的音訊或視訊流量的頻寬原則。

在 CAC 部署範例中，北美地區有六個網站。 這些網站的三種會受限於 WAN 頻寬： 雷諾、 波特蘭，與阿布。 其他三個站台，也就是*不*受限制的 WAN 頻寬： 紐約、 芝加哥與底特律。 如需如何建立或修改這些其他網路網站的範例，請參閱[建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-create-or-modify-a-network-site.md)。

若要檢視範例網路拓撲，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。

<div class=" ">


> [!NOTE]  
> 下列程序，Lync Server 管理命令介面用來建立網路網站。 如需使用 Lync Server 控制台建立網路網站的詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-network-site.md">建立或修改 Lync Server 2013 中的網路網站</A>。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>若要建立通話許可控制的網路網站

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行**New-csnetworksite** cmdlet 建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。 例如，執行：
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  若要完成建立整個範例拓撲的網站，請針對 EMEA 和 APAC 地區中受頻寬限制的網站重複步驟 2。

</div>

</div>

<span> </span>

</div>

</div>

</div>

