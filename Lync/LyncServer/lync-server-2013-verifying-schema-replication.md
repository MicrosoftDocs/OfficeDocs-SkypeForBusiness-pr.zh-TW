---
title: Lync Server 2013：驗證架構複寫
description: Lync Server 2013：驗證架構複寫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560169"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>在 Lync Server 2013 中驗證 Active Directory 架構複寫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

在您執行樹系準備之前，請手動驗證架構磁碟分割是否已複製。

<div>

## <a name="to-manually-verify-schema-replication"></a>手動驗證架構複寫

1.  以 Enterprise Admins 群組成員的身分登入網域控制站。

2.  依序按一下 **[開始]**、**[系統管理工具]** 和 **[ADSI 編輯器]**，以開啟 [ADSI 編輯器]。
    
    <div>
    

    > [!TIP]  
    > 或者，您可以從命令列執行 <STRONG>adsi services.msc</STRONG> 。

    
    </div>

3.  在 Microsoft Management Console (MMC) 樹中，如果尚未選取它，請按一下 [ **ADSI 編輯器**]。

4.  在 **[執行]** 功能表上，按一下 **[連線到]**。

5.  在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。

6.  在架構容器下，搜尋 CN=ms-RTC-SIP-SchemaVersion。 如果此物件存在，而 **rangeUpper** 屬性的值為 1150，**rangeLower** 屬性的值為 3，則表示已成功更新和複寫架構。 如果此物件不存在，或 **rangeUpper** 和 **rangeLower** 屬性不是上述指定的值，則表示未修改或未複寫架構。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中執行 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)  


[在 Lync Server 2013 中準備 Active Directory 架構](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

