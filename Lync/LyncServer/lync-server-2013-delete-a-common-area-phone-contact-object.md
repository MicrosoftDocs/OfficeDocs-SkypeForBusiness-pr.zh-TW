---
title: Lync Server 2013：刪除常見的區域電話連絡人物件
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
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中刪除常見的區域電話連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可能會想要刪除與常見區域手機相關聯的連絡人物件。 例如，如果您將手機從員工椅中移除，就不需要有連絡人物件與該手機建立關聯。 **CsCommonAreaPhone** Cmdlet 提供一種刪除常見區域電話帳戶的方式。 當您執行此 Cmdlet 時，系統會從**CsCommonAreaPhone**傳回的常用區域電話清單中刪除該手機。 此外，與該手機相關聯的連絡人物件會從 Active Directory 網域服務中刪除。

使用 [**移除-CsCommonAreaPhone** ] 來移除一個常見的區域電話或所有具有共同元素（例如顯示名稱或國家/地區代碼）的常見區域電話。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>移除指定的通用區域電話

  - 下列命令會移除含 SIP 位址 sip:mainlobby@litwareinc.com 的通用區域手機：
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>根據使用者的顯示名稱移除通用區域電話

  - 這個命令會移除顯示名稱包含字串值 "建築物 14" 的所有常見區域手機：
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>根據國家/地區代碼移除通用區域手機

  - 這個命令會移除美國所有常見的區域電話（國家/地區碼1）和區號425：
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

如需詳細資訊，請參閱[Remove CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

