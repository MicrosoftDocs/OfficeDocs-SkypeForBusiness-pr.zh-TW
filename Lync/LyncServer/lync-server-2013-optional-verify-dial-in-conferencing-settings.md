---
title: Lync Server 2013： (選用) 驗證電話撥入式會議設定
description: Lync Server 2013： (選用) 驗證電話撥入式會議設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec002cfbd7cdd67498768a360143f88ab4f8e1b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572559"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a> (選用) 驗證 Lync Server 2013 中的電話撥入式會議設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-02_

做為您的電話撥入式會議設定的最終驗證，您可以搜尋撥號對應表，該撥號對應表中的電話撥入式會議地區未使用任何存取號碼，且未指定電話撥入式會議區域的存取號碼。 這是選擇性的步驟。

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>使用電話撥入式會議地區未使用的存取號碼來尋找撥號對應表

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    此 Cmdlet 會傳回所有電話撥入式會議地區未由存取號碼使用的撥號對應表。

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>尋找未指派地區的存取號碼

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    此 Cmdlet 會傳回與地區無關聯的所有電話撥入式會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

