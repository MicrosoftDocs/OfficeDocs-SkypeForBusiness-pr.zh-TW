---
title: Lync Server 2013：將使用者遷移至整合連絡人存放區
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
ms.openlocfilehash: 3ab00e89c41b075e47d7764ce1c9c4cd3c471b8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513630"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中將使用者遷移至整合連絡人存放區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-15_

當使用者執行下列動作時，使用者的連絡人會自動遷移至 Exchange 2013 伺服器：

  - 已指派了 UcsAllowed 設為 True 的使用者服務原則。

  - 已布建與 Exchange 2013 信箱，且至少已登入至信箱一次。

  - 使用 Lync 2013 豐富型用戶端登入。

如果使用者登入 Lync 2010 或更早版本的用戶端，或使用者未連線到 Exchange 2013 伺服器，則會略過使用者服務原則，且使用者的連絡人仍保留在 Lync Server 中。

您可使用下列方法之一，來判斷使用者的連絡人是否已移轉：

  - 檢查用戶端電腦上的下列登錄機碼：
    
    HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ \<SIP URL\> \\ UCS
    
    如果使用者的連絡人儲存在 Exchange 2013 中，則此機碼會包含值為2165的 InUCSMode。

  - 執行 **Test-CsUnifiedContactStore** Cmdlet。 在 [Lync Server 管理命令介面] 命令列上輸入：
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。

</div>

<span> </span>

</div>

</div>

</div>

