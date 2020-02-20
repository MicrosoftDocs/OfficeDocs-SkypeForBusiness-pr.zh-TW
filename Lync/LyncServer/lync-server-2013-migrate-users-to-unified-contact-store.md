---
title: Lync Server 2013： 將使用者移轉至整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09897effe252f49eda73fea567d9b54bdc8ad52a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>將使用者移轉至 Lync Server 2013 中整合連絡人存放區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 10 月 15_

使用者的連絡人就會自動移轉至 Exchange 2013 伺服器時使用者：

  - 已指派了 UcsAllowed 設為 True 的使用者服務原則。

  - 已佈建與 Exchange 2013 信箱，並已至少一次登入信箱。

  - 使用 Lync 2013 豐富型用戶端中記錄。

如果使用者登入 Lync 2010 或更早的用戶端，或者如果使用者未連線至 Exchange 2013 伺服器，則會忽略使用者服務原則及使用者的連絡人會保留在 Lync Server。

您可使用下列方法之一，來判斷使用者的連絡人是否已移轉：

  - 檢查用戶端電腦上的下列登錄機碼：
    
    HKEY\_目前\_使用者\\軟體\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    如果使用者的連絡人會儲存在 Exchange 2013 中，此機碼會包含 InUCSMode 值為 2165年的值。

  - 執行 **Test-CsUnifiedContactStore** Cmdlet。 在 Lync Server 管理命令介面命令列中，輸入：
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。

</div>

<span> </span>

</div>

</div>

</div>

