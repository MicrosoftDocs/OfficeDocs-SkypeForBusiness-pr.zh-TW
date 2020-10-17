---
title: Lync Server 2013：刪除公共區域電話連絡人物件
description: Lync Server 2013：刪除公共區域電話連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566599"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中刪除公共區域電話連絡人物件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可能想要刪除與公共區域電話相關聯的連絡人物件。 例如，如果您移除員工前往中的電話，則不需要有與該電話相關聯的 contact 物件。 **Remove-CsCommonAreaPhone** Cmdlet 提供一種方法，讓您刪除公用區域電話帳戶。 當您執行此 Cmdlet 時，系統會從 **Get-CsCommonAreaPhone**傳回的常見區域電話清單中刪除電話。 此外，會從 Active Directory 網域服務中刪除與該電話相關聯的連絡人物件。

使用 **Remove-CsCommonAreaPhone** 來移除一個共同區域電話或所有具有共同元素的公共區域電話，例如顯示名稱或國家/地區碼和區號。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>移除指定的公共區域電話

  - 下列命令會移除帶有 SIP 位址 sip:mainlobby@litwareinc.com 的公共區域電話：
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>根據顯示名稱移除公共區域電話

  - 此命令會移除顯示名稱包含字串值 "組建 14" 的所有公共區域電話：
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>根據國家/地區碼移除公共區域電話

  - 此命令會移除美國 (國家碼 1) 和區號425的所有通用區域電話：
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

如需詳細資訊，請參閱 [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

