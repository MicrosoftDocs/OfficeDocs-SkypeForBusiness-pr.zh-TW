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
ms.openlocfilehash: 7134afbc86134471e8d536b36fc8e28142a64db2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a>在 Lync Server 2013 中搜尋 Lync Server 使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-14_

您可以使用搜尋查詢的結果來設定 Lync Server 2013 的使用者。 您可以依顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）來搜尋使用者。

您可以使用 Lync Server [控制台] 或 [Active Directory 使用者和電腦] 管理單元來搜尋使用者。 下列程式說明如何使用 Lync Server 的 [控制台] 搜尋使用者。

<div>


> [!NOTE]  
> 在具有中央林拓撲的環境中，當您使用使用者的電子郵件地址搜尋使用者時，搜尋結果可能不正確。 相反地，您可以透過指定 SIP 位址首碼（例如 sip： name、新增搜尋篩選器，然後選取包含部分電子郵件地址的 SIP 位址）來搜尋使用者，或使用<STRONG>move-csuser</STRONG> Cmdlet。



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a>搜尋一或多位使用者

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您要搜尋之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、SAM 帳戶名稱、SIP 位址或行 URI，然後按一下 [**尋找**]。

5.  可選指定額外的搜尋準則以縮小結果範圍：
    
    1.  按一下 [**搜尋結果**] 上方畫面右上角的展開箭號按鈕，然後按一下 [**新增篩選**]。
    
    2.  輸入使用者屬性或按一下下拉式清單中的箭號，以選取使用者屬性。
    
    3.  在 [**等於**] 清單中，按一下 [**等於**或**不等於**]。
    
    4.  在文字方塊中，輸入您要用來篩選搜尋結果的搜尋準則，然後按一下 [**尋找**]。

6.  搜尋結果會顯示在 [**搜尋結果**] 下。 您可以選取清單中的任何或所有使用者，並在您選取的使用者上執行設定工作。

</div>

<div>

## <a name="see-also"></a>請參閱


[查看已針對 Lync Server 2013 啟用的使用者帳戶資訊](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

