---
title: Lync Server 2013：搜尋 Lync Server 使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f503736b22453f6c3aafd76bc2fac7211f11dec7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>在 Lync Server 2013 中搜尋 Lync Server 使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-14_

您可以使用搜尋查詢的結果來設定 Lync Server 2013 的使用者。 您可以依顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別元 (URI) 來搜尋使用者。

您可以使用 Lync Server 控制台或 Active Directory 使用者和電腦嵌入式管理單元來搜尋使用者。 下列程式說明如何使用 Lync Server 控制台來搜尋使用者。

<div>


> [!NOTE]  
> 在具有中央樹系拓撲的環境中，如果以使用者的電子郵件地址來搜尋使用者，搜尋結果可能會不正確。 您可以改為指定 SIP 位址首碼 (例如 sip:name) 來進行搜尋、新增搜尋篩選並選取包含部分電子郵件位址的 SIP 位址，或使用 <STRONG>Get-CSUser</STRONG> Cmdlet。



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>若要搜尋一個或多個使用者

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 **[搜尋使用者]** 方塊中，輸入您要搜尋之使用者帳戶的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或線路 URI 的全部或頭幾個字，然後按一下 **[尋找]**。

5.  (選用) 指定其他搜尋條件，縮減結果：
    
    1.  按一下畫面右上角就在 **[搜尋結果]** 上方的展開箭頭，然後按一下 **[新增篩選]**。
    
    2.  輸入使用者內容，您可以直接輸入文字或是按一下下拉式清單的箭頭以選取使用者內容。
    
    3.  在 **[等於]** 清單中，按一下 **[等於]** 或 **[不等於]**。
    
    4.  在文字方塊中，輸入您要用來篩選搜尋結果的搜尋條件，然後按一下 **[尋找]**。

6.  搜尋結果會出現在 **[搜尋結果]** 下方。您可以選取清單中任一或全部使用者，然後對所選使用者執行設定工作。

</div>

<div>

## <a name="see-also"></a>另請參閱


[查看啟用 Lync Server 2013 之使用者帳戶的相關資訊](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

