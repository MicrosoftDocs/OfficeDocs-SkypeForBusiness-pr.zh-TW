---
title: Lync Server 2013：將使用者移轉到整合的連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者移轉到整合的連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

當使用者在下列情況下，使用者的連絡人會自動轉移至 Exchange 2013 伺服器：

  - 已指派 UcsAllowed 設定為 True 的使用者服務原則。

  - 已使用 Exchange 2013 信箱進行預配，且至少已在信箱中登入一次。

  - 使用 Lync 2013 胖用戶端登入。

如果使用者使用 Lync 2010 或較舊版本的用戶端登入，或者如果使用者未連線到 Exchange 2013 伺服器，則系統會忽略使用者服務原則，且使用者的連絡人會保留在 Lync Server 中。

您可以使用下列其中一種方法來判斷使用者的連絡人是否已被遷移：

  - 檢查用戶端電腦上的下列登錄機碼：
    
    HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\\15.0\\\<Lync SIP\>\\URL UCS
    
    如果使用者的連絡人儲存在 Exchange 2013 中，此索引鍵會包含值為2165的 InUCSMode 值。

  - 執行**Test CsUnifiedContactStore** Cmdlet。 在 Lync Server Management Shell 命令列上，輸入：
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    如果**CsUnifiedContactStore**成功，則使用者的連絡人已遷移至整合連絡人存放區。

</div>

<span> </span>

</div>

</div>

</div>

