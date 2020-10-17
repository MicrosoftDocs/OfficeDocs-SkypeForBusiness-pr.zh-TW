---
title: Lync Server 2013：建立網路網站間原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c8523fe86cfee7b9e2332e459959b096831abb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515590"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a>在 Lync Server 2013 中建立網路站間原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

*網路網站間原則*定義在其間具有直接 WAN 連結的網站之間的頻寬限制。

如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - [新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 只有在兩個網站之間有直接的交叉連結時， <EM>才</EM> 需要網路網站間原則。



</div>

在「北美地區」範例中，雷諾與阿布奎基網站之間有直接連結。 這兩個網站需要套用適當頻寬原則設定檔的站間原則。 下列範例會套用 20Mb \_ 連結設定檔。

<div>

## <a name="to-create-a-network-intersite-policy"></a>建立網路站間原則

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行 New-CsNetworkInterSitePolicy Cmdlet，以建立網路網站間原則，並為具有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。 例如，執行：
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  如有需要，請重複步驟2，為所有具有直接交叉連結的網路網站配對建立網路網站間原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

