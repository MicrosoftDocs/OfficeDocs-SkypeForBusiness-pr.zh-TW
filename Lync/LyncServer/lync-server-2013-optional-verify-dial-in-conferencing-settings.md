---
title: 'Lync Server 2013: （選用） 驗證電話撥入式會議設定'
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
ms.openlocfilehash: 5bff47410f46516061a5a3be64bce17476b453e7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>（選用）確認 Lync Server 2013 中的撥入式會議設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010年-11-02_

為您的撥入式會議組態的最終驗證，您可以搜尋有未由任何存取號碼撥入式會議地區的撥號對應表計劃，以及沒有制定撥入式會議地區的存取號碼。 此步驟是選用的。

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>若要尋找與未由任何存取號碼撥入式會議地區的撥號對應表計劃

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    此 cmdlet 會傳回所有具有不是由任何存取號碼撥入式會議地區的撥號對應表計劃。

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>若要尋找沒有指派之地區的存取號碼

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    此 cmdlet 會傳回與地區不相關的所有電話撥入式會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

