---
title: 'Lync Server 2013: Cmdlet 執行架構準備'
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
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>確認 Lync Server 2013 中的 Active Directory 架構準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

執行樹系準備之前，請手動驗證架構磁碟分割已複寫。

<div>

## <a name="to-manually-verify-schema-replication"></a>若要手動驗證架構複寫

1.  以 Enterprise Admins 群組成員身分登入網域控制站。

2.  依序按一下 **[開始]**、**[系統管理工具]** 和 **[ADSI 編輯器]**，以開啟 [ADSI 編輯器]。
    
    <div>
    

    > [!TIP]  
    > 或者，您可以從命令列執行<STRONG>adsiedit.msc</STRONG> 。

    
    </div>

3.  在 Microsoft Management Console (MMC) 樹狀目錄中，如果未選取，按一下 [ **Adsi 編輯器]**。

4.  在 **[執行]** 功能表上，按一下 **[連線到]**。

5.  在 **[選取熟知的命名內容]** 的 **[連線設定]** 對話方塊中，選取 **[架構]**，然後按一下 **[確定]**。

6.  在架構容器下，搜尋 CN=ms-RTC-SIP-SchemaVersion。 如果此物件存在，而 **rangeUpper** 屬性的值為 1150，**rangeLower** 屬性的值為 3，則表示已成功更新和複寫架構。 如果此物件不存在，或 **rangeUpper** 和 **rangeLower** 屬性不是上述指定的值，則表示未修改或未複寫架構。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中執行 Active Directory 架構準備](lync-server-2013-running-schema-preparation.md)  


[準備 Lync Server 2013 中的 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

