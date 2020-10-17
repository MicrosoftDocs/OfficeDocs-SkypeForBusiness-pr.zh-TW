---
title: Lync Server 2013：請確定撥號對應表具有指派的區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9f9a67a65b870edd75259bca7c74a1fae2749f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534560"
---
# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>確定撥號對應表 Lync Server 2013 具有指派的區域

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-02_

用於電話撥入式會議的撥號對應表，需要指定 **[電話撥入式會議區域]**，才能讓電話撥入式會議存取號碼與適當的撥號對應表產生關聯。設定撥號對應表時，您會指定適用於該撥號對應表的電話撥入式會議區域。之後建立撥入存取號碼時，您會選取使存取號碼關聯至適當撥號對應表的區域。

因為替所有撥號對應表指定區域十分重要，因此建議您使用以下程序來確認所有撥號對應表都具有區域。這是選用步驟。

使用 **Get-CsDialPlan** Cmdlet 確認是否已為所有電話撥入式會議撥號對應表設定區域。 如果撥號對應表缺少區域，您可以使用 **Set-CsDialPlan** Cmdlet 來設定區域。 您也可以使用 Lync Server 控制台更新現有撥號對應表中的區域。 如需使用 Lync Server 控制台的詳細資訊，請參閱 [在 Lync server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>若要確認撥號對應表是否已設定區域屬性

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    例如：
    
        Get-CsDialPlan
    
    在此範例中，會傳回組織中所有已設定的撥號對應表。

4.  檢閱傳回的撥號對應表，檢查是否有任何一項缺少電話撥入式會議區域。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>若要設定撥號對應表的區域屬性

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  針對任何缺少電話撥入式會議區域的撥號對應表，執行：
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    例如：
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    在此範例中，將修改識別為 Redmond 的撥號對應表，以將其 DialinConferencingRegion 屬性設為 "US West Coast"。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

