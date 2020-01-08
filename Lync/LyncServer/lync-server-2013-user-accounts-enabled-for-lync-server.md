---
title: Lync Server 2013：已啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>已啟用 Lync Server 2013 的使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-18_

本節中的主題提供設定使用者設定的逐步程式，您可以使用 Lync Server 2013 控制台進行設定。

<div>


> [!IMPORTANT]  
> 您無法使用 Lync Server [控制台] 來管理屬於 Active Directory 網域系統管理員群組成員的使用者。 對於網域管理員使用者，您只能使用 Lync Server [控制台] 執行唯讀搜尋作業。 若要在網域管理員使用者上執行寫入操作（例如，針對 Lync Server [控制台] 啟用或停用，請變更池或原則指派，電話設定，SIP 位址），您必須在以網域管理員使用者身分登入的情況下，才能使用 Windows PowerShell Cmdlet。 如需使用 Windows PowerShell Cmdlet 來管理使用者的詳細資料，請參閱<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面。



</div>

當您執行任何涉及搜尋使用者或篩選使用者搜尋結果的 Lync Server 2013 系統管理工作時，會有一些使用者屬性作為屬性存在於 Active Directory 網域服務中，但不會複製到通用類別目錄在部署 Microsoft Exchange Server 之前。 Microsoft Exchange （而非 Lync Server）會將下列屬性標示為在安裝時，將其複製到全域編目：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者資訊</th>
<th>位址和電話</th>
<th>組織</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中間</p></td>
<td><p>街道位址</p>
<p>國家/地區</p>
<p>值班</p>
<p>傳入</p>
<p>行動裝置</p></td>
<td><p>職稱</p>
<p>家</p>
<p>部門</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本節內容

  - [查看已針對 Lync Server 2013 啟用的使用者帳戶資訊](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [在 Lync Server 2013 中管理企業版使用者語音](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)

  - [在 Lync Server 2013 中管理外部使用存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中指派每個使用者的原則](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的使用者管理 Cmdlet](lync-server-2013-user-management-cmdlets.md)  


[在 Lync Server 2013 中管理使用者](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

