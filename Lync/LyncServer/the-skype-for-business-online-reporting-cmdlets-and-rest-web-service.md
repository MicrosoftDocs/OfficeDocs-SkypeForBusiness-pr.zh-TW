---
title: Skype 商務 Online 報告指令程式和 REST web 服務
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
ms.openlocfilehash: 0476b90659ced152a4d24fbb3890ac224bdf0d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Skype 商務 Online 報告指令程式和 REST web 服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-09-05_

搭配報告功能，商務用 Skype 會提供存取五個 Windows PowerShell cmdlet 幫助產生這些報告，而且也可用於系統管理員所傳回的自訂報告的資料。 Skype 商務 Online 也包含 REST (Representational State Transfer)，可以由開發人員用來擷取自訂報告的資訊。

系統管理員可報告指令程式包括：

  - Get-CsActiveUserReport，其提供作用中的使用者 （也就是使用者已登入 Skype for Business Online 並參與至少一個會議或對等通訊工作階段） 之數目的相關資訊。

  - 在 [音訊/視訊會議所花費的 Get-csavconferencetimereport，其提供的時間 （以分鐘為單位） 的使用者數量的相關資訊。

  - Get-csconferencereport，提供資訊的數量和類型的會議使用者參與。

  - Get-csp2pavtimereport，可提供包含音訊和/或視訊的端對端工作階段中所花費的時間 （以分鐘為單位） 使用者的數量的相關資訊。

  - Get-csp2psessionreport，其提供的數量和類型的使用者參與的對等工作階段的相關資訊。

大部分的系統管理員會使用 Microsoft 365 系統管理中心中的可用的報告： 不只是這些報告自動產生，但它們也會提供更容易解譯比所傳回的原始號碼值的資料的圖形表示報告指令程式。 不過，系統管理員熟悉 Windows PowerShell cmdlet 可用於報告傳回未備妥從 Lync Online 報告的資料。 例如，報告指令程式傳回工作階段期間的相關資訊 （以分鐘為單位，每個工作階段持續的時間量）。 個別的工作階段期間不提供使用 Lync Online 的報告。 同樣地，在每日檢視 Lync Online 報告顯示先前的 14 天的資訊。 如果您想要檢閱每日總計將不同的日期 （例如，從四個月以前的日期） 您可以使用報告指令程式來執行此動作。

系統管理員也可能會感興趣的文件中[使用 Excel 擷取 Office 365 報表資料](http://msdn.microsoft.com/library/dn781442.aspx)，以及說明如何使用 Microsoft Excel 中的 OData 資料查詢功能，來建立自訂的 office 365 報告。 自訂的報表可讓您能夠語音輸入的資料 （及多少資料） 會傳回從 Office 365 報告服務。 自訂報告也可讓您指定應該如何排序及群組，資料的變得和提供存取不會顯示在系統管理中心中的資訊。

具有開發背景的系統管理員可以使用 REST web 服務以取得未顯示在 Skype 商務 Online 系統管理中心中的資訊。 REST 服務的類似的 SOAP 服務，在於每項技術提供用戶端與伺服器之間傳輸 XML 資料的方式。 不過，REST 服務有至少兩個優點透過 SOAP 服務。 其中，其餘部分會執行使用標準化的格式，又稱為 ATOM 整合格式的 XML 資料傳輸。 相反地，SOAP 傳送資料時使用非標準格式。 此外，其餘部分會能夠跨封鎖 HTTP 動詞 GET 與文章以外的網路傳送資料。

<div>

## <a name="see-also"></a>另請參閱


[Lync Online 報告](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Office 365 報告 Web 服務](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[了解 Office 365 報告 Web 服務](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Exchange Online 報告 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[使用 Excel 擷取 Office 365 報表資料](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

