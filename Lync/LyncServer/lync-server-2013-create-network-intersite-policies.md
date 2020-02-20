---
title: Lync Server 2013： 建立網站間原則
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
ms.openlocfilehash: f1c42f9edf30e7581d001b2e6bd2e79ea5a3c76a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Lync Server 2013 中建立網站間原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

*網站間原則*會定義有直接的 WAN 連結它們之間的站台之間的頻寬限制。

如需詳細資訊，請參閱 Lync Server 管理命令介面文件的下列 cmdlet:

  - [新 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 如果兩個網路站台之間沒有直接的交叉連結，則需要<EM>唯一</EM>網站間原則。



</div>

在範例拓撲北美地區中，有雷諾與阿布站台之間是直接連結。 這兩個網站需要套用適當的頻寬原則設定檔的站台間原則。 下列範例會將套用 20mb\_連結設定檔。

<div>

## <a name="to-create-a-network-intersite-policy"></a>若要建立網站間原則

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  執行新增 CsNetworkInterSitePolicy cmdlet 來建立網站間原則並套用具有直接交叉連結的兩個站台的適當的頻寬原則設定檔。 例如，執行：
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  重複步驟 2，視需要建立網站間原則的所有網站配對具有直接交叉連結。

</div>

</div>

<span> </span>

</div>

</div>

</div>

