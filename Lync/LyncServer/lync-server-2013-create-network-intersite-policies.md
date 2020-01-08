---
title: Lync Server 2013：建立網路站間原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路站間原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

*網路站間原則*定義在它們之間有直接 WAN 連結的網站之間的頻寬限制。

如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - [新-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 只有在兩個網路網站之間有直接的交叉連結時，<EM>才</EM>需要網路網站間原則。



</div>

在北美的 [北美] 地區，Reno 和 Albuquerque 網站之間有直接連結。 這兩個網站需要一個能套用適當頻寬原則設定檔的網站間原則。 下列範例會套用 20Mb\_連結設定檔。

<div>

## <a name="to-create-a-network-intersite-policy"></a>建立網路站間原則

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行新的 CsNetworkInterSitePolicy Cmdlet 來建立網路站間原則，並針對有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。 例如，執行：
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  視需要重複步驟2，為擁有直接交叉連結的所有網路網站配對建立網路網站間原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

