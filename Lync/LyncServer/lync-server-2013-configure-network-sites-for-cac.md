---
title: Lync Server 2013：設定 CAC 的網路網站
description: Lync Server 2013：設定 CAC 的網路網站。
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
ms.openlocfilehash: 24adbbb1f5ee46618c685e072d519a338cb9b0af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564999"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中設定 CAC 的網路網站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> 如果您已建立 E9-1-1 或媒體旁路的網站，您可以修改現有的網路網站，以使用 <STRONG>Set-CsNetworkSite</STRONG> Cmdlet 來套用頻寬原則設定檔。 如需如何修改網路網站的範例，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中建立或修改網站</A>。



</div>

*網路網站* 是通話許可控制之每個網路地區內的辦公室或位置 (CAC) 、E9-1-1 和 media 旁路部署。 使用下列程式來建立網路網站，使其對應至 CAC 的範例網路拓撲中的網站。 這些程式示範如何建立及設定受 WAN 頻寬限制的網站，因此需要頻寬原則來限制即時音訊或視頻流量流程。

在範例 CAC 部署中，北美地區包含六個網站。 以下是受 WAN 頻寬限制的三個網站：雷諾、上海及阿布奎基。 其他三個網站 *不* 受 WAN 頻寬限制：紐約、芝加哥和底特律。 如需如何建立或修改其他網路網站的範例，請參閱 [在 Lync Server 2013 中建立或修改網站](lync-server-2013-create-or-modify-a-network-site.md)。

若要查看範例網路拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

<div class=" ">


> [!NOTE]  
> 在下列程式中，Lync Server 管理命令介面是用來建立網路網站。 如需使用 Lync Server 控制台建立網路網站的詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中建立或修改網路網站</A>。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>為通話許可控制建立網路網站

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 **New-CsNetworkSite** Cmdlet 來建立網路網站，並將適當的頻寬原則設定檔套用至每個網站。 例如，執行：
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  若要完成整個範例拓撲的建立網站，請對 EMEA 和 APAC 地區的頻寬限制網路網站重複步驟2。

</div>

</div>

<span> </span>

</div>

</div>

</div>

