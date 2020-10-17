---
title: 商務用 Skype Online 報告 Cmdlet 和 REST web 服務
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92f2be5987ad6ffc76d19e7ccad81da4115487a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514950"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>商務用 Skype Online 報告 Cmdlet 和 REST web 服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-05_

與報表功能搭配使用，商務用 Skype Online 可讓您存取五個 Windows PowerShell Cmdlet，以協助產生這些報告，而且也可供系統管理員用來傳回自訂的報表資料。 商務用 Skype Online 也包含 REST (代表性狀態轉移) ，可供開發人員用來檢索自訂的報表資訊。

系統管理員可以使用的報告 Cmdlet 包括：

  - Get-CsActiveUserReport，提供作用中使用者數目的相關資訊， (即登入商務用 Skype Online 的使用者，以及至少參加一部會議或對等通訊會話) 的使用者。

  - Get-CsAVConferenceTimeReport，提供在音訊/視訊會議中， (以分鐘為單位的時間量資訊) 使用者。

  - Get-CsConferenceReport，提供使用者參與之會議的數量和類型的相關資訊。

  - Get-CsP2PAVTimeReport，此資訊提供 (以分鐘為單位的時間量資訊，) 使用者在包含音訊和/或影片的點對點工作階段中所花費的時間。

  - Get-CsP2PSessionReport，提供使用者參與的點對點工作階段的數量和類型的相關資訊。

大部分系統管理員會使用 Microsoft 365 系統管理中心提供的報告：這不僅是自動產生的報告，也提供了資料的圖形表示，但通常會比對報告指令程式所傳回的原始數位值更為容易轉譯。 不過，熟悉 Windows PowerShell 的系統管理員可以使用報告 Cmdlet，傳回 Lync Online 報告中無法輕易提供的資料。 例如，報告 Cmdlet 會傳回會話持續時間的資訊， (每個會話持續) 的時間量（以分鐘為單位）。 使用 Lync Online 報告無法使用個別的會話持續時間。 同樣地，在 [每日] 視圖中，Lync Online 報告只會顯示過去14天的資訊。 如果您想要查看不同日的每日匯總 (例如，從四個月前開始的日期) 您可以使用報告 Cmdlet 來執行這項作業。

管理員可能也會有興趣 [使用 Excel 來檢索 Office 365 報告資料](https://msdn.microsoft.com/library/dn781442.aspx)，這會說明如何使用 Microsoft Excel 中的 OData 資料查詢功能來建立自訂 Office 365 報告。 自訂報告讓您能夠口述哪些資料 (，以及 Office 365 報表服務傳回多少資料) 。 自訂報告也可讓您執行下列動作：指定資料的排序和群組方式，並提供系統管理員中心未顯示資訊的存取權。

具有開發背景的系統管理員可以使用 REST web 服務，以取得未顯示在商務用 Skype Online 系統管理中心中的資訊。 REST 服務與 SOAP 服務類似，每個技術都提供一種方法，可在用戶端與伺服器之間傳輸 XML 資料。 不過，REST 服務與 SOAP 服務具有至少兩個優點。 若為 one，REST 會使用稱為 ATOM 供稿格式的標準化格式來執行 XML 資料傳輸。 相比之下，在傳輸資料時使用非標準格式的 SOAP。 此外，REST 可以跨封鎖接收和公告以外之 HTTP 動詞的網路傳輸資料。

<div>

## <a name="see-also"></a>另請參閱


[Lync Online 報告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Office 365 報告 Web 服務](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[瞭解 Office 365 報告 Web 服務](https://msdn.microsoft.com/library/office/jj984321.aspx)  
[Exchange Online 報告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[使用 Excel 擷取 Office 365 報表資料](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

