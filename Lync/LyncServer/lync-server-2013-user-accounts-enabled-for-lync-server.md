---
title: Lync Server 2013：已啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccef1e811d4ccd6b54350d6678a6b089eb4caafd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>啟用 Lync Server 2013 的使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-18_

本節中的主題提供逐步程式，以設定您可以使用 Lync Server 2013 控制台執行的使用者設定。

<div>


> [!IMPORTANT]  
> 您無法使用 Lync Server 控制台來管理屬於 Active Directory Domain Admins 群組成員的使用者。 針對 Domain Admins 使用者，您可以使用 Lync Server 控制台只執行唯讀的搜尋作業。 若要在 Domain Admins 使用者上執行寫入作業 (例如，啟用或停用 Lync Server 控制台、變更集區或原則指派、電話語音設定、SIP 位址) ，您必須在以 Domain Admins 使用者的身分登入時使用 Windows PowerShell Cmdlet。 如需使用 Windows PowerShell Cmdlet 來管理使用者的詳細資訊，請參閱 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面。



</div>

當您執行任何需要搜尋使用者或篩選使用者搜尋結果的 Lync Server 2013 系統管理工作時，會有一些使用者屬性存在於 Active Directory 網域服務中，但在部署 Microsoft Exchange Server 之前，不會複製到通用類別目錄。 Microsoft Exchange 不是 Lync Server，當安裝時，會將下列屬性標示為已安裝的通用類別目錄：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者資訊</th>
<th>地址和電話</th>
<th>組織</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>縮寫</p></td>
<td><p>街道地址</p>
<p>國家/地區</p>
<p>呼叫器</p>
<p>傳真</p>
<p>行動裝置</p></td>
<td><p>職稱</p>
<p>Company</p>
<p>部門</p>
<p>辦公室</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>本章節內容

  - [查看啟用 Lync Server 2013 之使用者帳戶的相關資訊](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [在 Lync Server 2013 中管理使用者的企業語音](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)

  - [在 Lync Server 2013 中管理外部存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中指派每一使用者原則](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的使用者管理 Cmdlet](lync-server-2013-user-management-cmdlets.md)  


[在 Lync Server 2013 中管理使用者](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

