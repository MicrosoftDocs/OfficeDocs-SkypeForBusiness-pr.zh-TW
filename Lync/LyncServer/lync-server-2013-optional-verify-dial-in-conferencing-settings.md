---
title: Lync Server 2013：(選用) 驗證電話撥入式會議設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>(選用) 在 Lync Server 2013 中驗證電話撥入式會議設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-02_

針對您的電話撥入式會議設定的最終驗證，您可以搜尋其電話撥入式會議區域不是由任何存取號碼所使用的撥號方案，以及尚未指定電話撥入式會議區域的存取號碼。 此為選用步驟。

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>若要尋找電話撥入式會議區域中的撥號方案（不是由存取號碼使用）

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    這個 Cmdlet 會傳回具有電話撥入式會議區域的所有撥號方案，這些方案不是由存取號碼所使用。

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>若要尋找沒有指定區域的存取號碼

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    這個 Cmdlet 會傳回與區域不相關的所有電話撥入式會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

