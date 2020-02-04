---
title: 商務用 Skype Online 報告 Cmdlet 和 REST web 服務
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf02e845acc35ff4381b43beb91d798ec49f58d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>商務用 Skype Online 報告 Cmdlet 和 REST web 服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-05_

與 [報告] 功能搭配使用時，商務用 Skype Online 提供五個 Windows PowerShell Cmdlet 的存取權，以協助產生這些報告，而且也可供系統管理員用來傳回自訂的報告資料。 商務用 Skype Online 也包含 REST （Representational 狀態傳輸），開發人員可使用這些功能來取得自訂的報告資訊。

系統管理員可使用的報告 Cmdlet 包括：

  - CsActiveUserReport，提供作用中使用者數的相關資訊（也就是已登入商務用 Skype Online 並參與至少一個會議或對等通訊會話的使用者）。

  - CsAVConferenceTimeReport，可提供使用者在音訊/視訊會議中花費的時間（分鐘）數的相關資訊。

  - CsConferenceReport，提供使用者參與之會議數量與類型的相關資訊。

  - CsP2PAVTimeReport，可提供使用者在點對點工作階段中所花費的時間（以分鐘為單位），其中包含音訊和/或影片的相關資訊。

  - CsP2PSessionReport，可提供使用者參與之點對點工作階段之數量與類型的相關資訊。

大多數系統管理員會使用 Microsoft 365 系統管理中心提供的報告：不只是那些自動產生的報表，但它們也提供資料的圖形化表示，這些資料通常容易解讀，而不是由所傳回的原始數值值報告 Cmdlet。 不過，熟悉 Windows PowerShell 的系統管理員可以使用報告 Cmdlet，傳回 Lync Online 報表中無法使用的資料。 例如，報告 Cmdlet 會傳回會話期間的相關資訊（每個會話持續的時間長度，以分鐘為單位）。 無法使用 Lync Online 報表來使用個別的會話期間。 同樣地，在 [每日] 視圖中，Lync Online 報告只會顯示前14天的資訊。 如果您想要查看不同日的每日總計（例如，四個月前的日期），您可以使用報表 Cmdlet 來執行此操作。

系統管理員可能也會對[使用 Excel 來取得 Office 365 報告資料](http://msdn.microsoft.com/en-us/library/dn781442.aspx)的文章感興趣，說明如何在 Microsoft Excel 中使用 OData 資料查詢功能來建立自訂的 Office 365 報表。 自訂報告可讓您指示從 Office 365 報表服務傳回哪些資料（以及多少資料）。 您也可以使用自訂報表來指定資料排序與分組的方式，以及提供不在系統管理中心顯示之資訊的存取權。

擁有開發背景的系統管理員可以使用 REST web 服務，來取得商務用 Skype Online 系統管理中心未顯示的資訊。 REST 服務與 SOAP 服務類似，因為每項技術都提供一種在用戶端與伺服器之間傳輸 XML 資料的方式。 不過，REST 服務至少有兩個與 SOAP 服務有關的優點。 若是一個，REST 會使用稱為 ATOM 供稿格式的標準化格式來執行 XML 資料傳輸。 相比之下，在傳輸資料時，使用非標準格式的 SOAP。 此外，REST 可以在封鎖除 [取得] 和 [張貼] 以外的 HTTP 動詞的網路上傳輸資料。

<div>

## <a name="see-also"></a>請參閱


[Lync Online 報告](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[Office 365 報告 Web 服務](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[瞭解 Office 365 報告 Web 服務](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Exchange Online 報告 Cmdlet](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[使用 Excel 來取得 Office 365 報告資料](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

