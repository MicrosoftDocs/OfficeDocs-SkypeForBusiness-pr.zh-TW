---
title: 商務用 Skype Server 中的 IP 電話清查報告
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: 摘要：瞭解商務用 Skype Server 中的 IP 電話清查報告。
ms.openlocfilehash: 9a09bc76d77c2290ab8e0f0c08fce79c2766e3a0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862460"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 IP 電話清查報告
 
**摘要：** 深入瞭解商務用 Skype Server 中的 IP 電話清查報告。
  
IP 電話清查報告報告組織中目前使用之 IP 電話的相關資訊。 IP 清查報告提供在指定報告期間實際使用的 IP 電話詳細清單。 除了其他事項之外，此報告還可讓系統管理員知道是否仍在使用任何舊的過期電話，而這些電話是否仍在使用中;此外，它也可以警示系統管理員，因為組織中有很少使用的電話很昂貴。 當購買新的電話或重新發佈現有的電話時，該類型的資訊可能非常寶貴。  (例如，很少使用他或她的昂貴電話的使用者，可能要求您將電話換用使用他或她之電話的使用者頻率較高。 ) 
  
請注意，此報告在用來做為真正的庫存報告時，會有一些限制。 一方面，IP 電話報告只會列出登入商務用 Skype Server 在指定期間內的所有電話，並依上次登入的時間排序。 如果電話沒有在指定的時間期間登入，則不會在庫存報告中列出。 ，包括在啟動期間之前登入的電話，而且在指定的時間間隔內仍會登入。 例如，假設您想要查看2015年7月的所有電話清點。 假設您也可以在2015年6月30日當電話登入商務用 Skype Server，而且在7月1日之後仍登入。 這些電話在7月1日的庫存報告上不會顯示。
  
此外，請務必注意，庫存報告可以包含您的組織不再使用的電話。 例如，假設您在2015年7月1日在系統上登入的 Fabrikam 電話數目。5天之後您的組織會擺脫所有的 Fabrikam 電話，並以新的 Contoso 模型取代。 Fabrikam 電話仍會出現在「清查」報告上，因為它們是在七月期間登入系統。
  
此外，IP 電話清查報告不會報告不同電話類型的摘要總數。 例如，假設您有 105 Polycom CX600 電話。 報告不會告訴您，您有105以上的電話;相反地，您只會看到 Polycom Cx600 的105個別專案。 Polycom Cx600 的105專案的唯一方法，就是手動統計每個專案。
  
> [!TIP]
> 或者，匯出資料，並使用 Microsoft Excel 或 Windows PowerShell 為您進行計數。 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>存取 IP 電話清查報告

IP 電話清查報告可從監控報告的首頁進行存取。 如果您按一下 [使用者 URI] 度量，您可以存取該使用者的使用者活動報告。 按一下對等通話的最後一個活動度量會帶您前往 Peer-to-Peer 會話詳細資料包告。按一下會議的相同公制會帶您前往會議詳細資料包告。
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 電話清查報告的最佳用法

如果您只對一種特殊電話的使用資訊感興趣 (例如，「使用 Polycom CX600 電話的使用者頻率為何？」。) 您可以透過篩選該特定類型的電話，直接從 IP 電話清查報告取得資訊。 不過，如果您想要所有電話的摘要資訊 (多少人使用的是 Polycom CX600、使用 LG-Nortel IP8540 的數目，等等。 ) 之後，您將需要匯出資料，並使用另一個應用程式 (例如 Windows PowerShell) 來執行該類型的分析。 例如，假設您會將資料匯出到逗號分隔值檔案 (C:\Data\IP_Phone_Inventory_Report.csv) 。 在這種情況下，您可以使用這兩個命令，提供您所有電話的摘要資料：
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

該命令將傳回類似下列的資料：
  
<pre>
Count    Name
-----    ----
  267    POLYCOM, CX700
  267    POLYCOM, CX600
  166    POLYCOM, C
   68    Microsoft, CPE
   64    LG-Nortel, IP8540
   59    Aastra, 6725ip
   37    LG-Nortel, IP
   22    POLYCOM, CX3000
   11    Microsoft, CPE_A
    9    POLYCOM, CX500
    7    Aastra, 6721ip
</pre>

同樣地，這兩個命令會告訴您登入系統的電話，但永不實際用來撥打電話 (最後一個活動度量值為空白，表示沒有任何上一個活動) ：
  
```PowerShell
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

針對每個尚未使用的電話，傳回類似以下的資料：
  
<pre>
Manufacturer     : POLYCOM
Hardware version : CX600
MAC address      : 00-04-F2-00-01-76
User URI         : 422
User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
Last logon time  : 8/30/2010 4:44:48 PM
Last logoff time : 8/30/2010 5:59:07 PM
Last activity    :
</pre>

使用 IP 電話清查報告的另一種有趣方式是：如果您有 IP 的 MAC 位址電話您可以在 [MAC 位址] 文字方塊中輸入該位址，即可找出最後一次使用該電話的使用者。 然後，[IP 電話清查] 報告會傳回 (其他專案中的其他專案，) 使用該電話上一次登入之使用者的 SIP 位址。 或者，您也可以在 [使用者 URI 前置詞] 方塊中輸入使用者 SIP 位址 (，) 以找出該使用者已使用的所有電話。
  
## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，IP 電話清查可讓您只查看特定公司製造的電話，甚至只查看這些電話的特定版本。 您也可以選擇資料的分組方式。 在此情況下，登記會依小時、日、周或月進行分組。
  
下表列出您可以搭配 IP 電話清查報告使用的篩選器。
  
**IP 電話清查報告篩選器**

|**名稱**|**描述**|
|:-----|:-----|
|**From** <br/> |時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**To** <br/> |時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：  <br/> 7/7/2015 1:00 PM  <br/> 如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：  <br/> 7/7/2015  <br/> 若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：  <br/> 7/3/2015  <br/> 星期永遠是從星期日開始星期六結束。  <br/> |
|**製造商** <br/> |製造 IP 電話的公司名稱。 根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。  <br/> |
|**硬體版本** <br/> |IP 電話的版本號碼;使用製造商和硬體版本篩選器，您可以唯一識別特定類型的電話。 根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。  <br/> |
|**使用者代理程式** <br/> |IP 電話所使用之軟體的識別碼。 根據目前資料庫中的 IP 電話，此篩選器的值會自動填入。  <br/> |
|**MAC 位址** <br/> |IP 電話上網路介面的唯一識別碼。 Media Access Control (MAC) 位址通常是在電話製造時，且硬接線到裝置硬體時進行指派。  <br/> 若要搜尋與特定 MAC 位址相關的記錄，只要輸入該位址即可。 例如：  <br/> 00-08-16-16-48  <br/> 您必須輸入完整的位址。 部分位址 (例如，00-08-5D) 不會傳回任何資料。  <br/> |
|**天數之前的最後一個活動** <br/> | 選取下列其中一個值： <br/>  一切 <br/>  10  <br/>  共 <br/>  大約 <br/> |
|**前一天的登出時間** <br/> | 選取下列其中一個值： <br/>  一切 <br/>  10  <br/>  共 <br/>  大約 <br/> |
|**使用者 URI 字首** <br/> |使用 IP 電話之使用者的 SIP 位址。  <br/> |
   
## <a name="metrics"></a>度量

下表列出 IP 電話庫存報告中提供的資訊。
  
**IP 電話清查報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**製造商** <br/> |是  <br/> |製造 IP 電話的公司名稱。  <br/> |
|**硬體版本** <br/> |是  <br/> |IP 電話的版本號碼。  <br/> |
|**MAC 位址** <br/> |是  <br/> |IP 電話上網路介面的唯一識別碼。 MAC 位址通常是在電話製造時所指派，而且會硬接線至裝置硬體。  <br/> |
|**使用者 URI** <br/> |是  <br/> |使用 IP 電話之使用者的 SIP 位址。  <br/> |
|**使用者代理程式** <br/> |是  <br/> |IP 電話所使用之軟體的識別碼。  <br/> |
|**上次登入時間** <br/> |是  <br/> |IP 電話上次登入商務用 Skype Server 的日期和時間。  <br/> |
|**上次登出時間** <br/> |是  <br/> |IP 電話上次從商務用 Skype Server 中登出的日期和時間。  <br/> |
|**最後一個活動** <br/> |是  <br/> |上次使用 IP 電話的日期和時間。  <br/> |
   

