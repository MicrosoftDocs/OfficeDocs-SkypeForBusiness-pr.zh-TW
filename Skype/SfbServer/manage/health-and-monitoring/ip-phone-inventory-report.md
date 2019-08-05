---
title: 商務用 Skype Server 中的 IP 電話清點報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
description: '摘要: 瞭解商務用 Skype Server 中的 IP 電話清點報告。'
ms.openlocfilehash: 8d7d7be6b5a677f3df33ebf2e0bb01f31b76eac9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193734"
---
# <a name="ip-phone-inventory-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 IP 電話清點報告
 
**摘要:** 瞭解商務用 Skype Server 中的 IP 電話清點報告。
  
IP 電話清點報告會報告貴組織目前正在使用之 IP 電話的相關資訊。 IP 清點報告提供在指定報告期間內實際使用之 IP 手機的詳細清單。 在其他專案中, 此報告可讓系統管理員知道是否有任何舊版、過時的手機仍在使用中, 而這些電話應該會被取代;此外, 它也可以提醒系統管理員在組織中有大量的電話很少使用的情況。 在購買新手機或重新發佈現有手機時, 這類資訊可能很有用。 (例如, 很少使用其昂貴手機的使用者, 可能會要求您以更頻繁的方式, 將手機更換為使用他或她的手機的使用者。)
  
請注意, 此報告在作為真正的庫存報告時, 會有一些限制。 在其中一種情況下, IP 電話報告只會列出在指定的時段內登入商務用 Skype 伺服器的所有電話, 並依其上次登入時間排序。 如果手機在指定的時段內沒有登入, 則不會列于庫存報告中。 這包括在時間週期開始之前登入, 且在指定的時間間隔期間仍登入的電話。 例如, 假設您想要查看2015年7月的所有電話清點。 假設您也是在2015年6月30日登入商務用 Skype Server 的數個電話, 而且在7月1日仍登入。 這些手機不會顯示在7月1日的庫存報告上。
  
另外, 請務必注意, 庫存報告可能包含貴組織已不再使用的電話。 例如, 假設您已在2015年7月1日登入系統的 Fabrikam 電話數。您的組織稍後會有5天的時間來移除所有這些 Fabrikam 手機, 並以較新的 Contoso 模型取代。 Fabrikam 手機仍會出現在 [清查] 報表上, 因為它們會在7月期間登入系統。
  
此外, IP 電話清點報告不會報告不同電話類型的摘要總數。 例如, 假設您有 105 Polycom CX600 電話。 報告不會告知您有105以上的手機;相反地, 您只會看到 105 Polycom Cx600 的個別專案。 若要知道 Polycom Cx600 有105專案, 只需手動計算每個專案。
  
> [!TIP]
> 或者, 匯出資料並使用 Microsoft Excel 或 Windows PowerShell 來為您計算。 
  
## <a name="accessing-the-ip-phone-inventory-report"></a>存取 IP 電話清點報告

[IP 電話清點] 報告是從 [監控報告] 首頁存取。 如果您按一下 [使用者 URI 規格], 您可以存取該使用者的使用者活動報告。 按一下對等呼叫的最後一個活動躍點數會將您帶到點對點工作階段詳細資料包告;按一下會議的同一個公制會將您帶到會議詳細資料包告。
  
## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>充分利用 IP 電話清點報告

如果您只對某種特定類型手機的使用資訊感興趣 (例如, 「使用 Polycom CX600 電話的使用者頻率如何？」), 您可以透過篩選特定類型的電話, 直接從 IP 電話清點報告取得該資訊。 不過, 如果您想要的是所有電話的摘要資訊 (有多少人使用 Polycom CX600, 還有多少是使用 LG-Nortel IP8540 等等), 那麼您將需要匯出資料並使用另一個應用程式 (例如 Windows PowerShell) 來執行該類型的分析. 例如, 假設您將資料匯出為逗點分隔值檔案 (C:\Data\IP_Phone_Inventory_Report.csv)。 在這種情況下, 您可以使用這兩個命令, 為您的所有手機提供摘要資料:
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending
```

這樣會傳回如下所示的資料:
  
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

同樣地, 這兩個命令會告知您登入系統的電話, 但永遠不會實際用來撥打電話 (最後一個活動指標的值為空白, 表示沒有任何最後一個活動):
  
```
$phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
$phones | Where-Object {$_."Last activity" -eq ""}
```

針對每個尚未使用的電話, 傳回如下所示的資料:
  
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

使用 IP 電話清點報告的另一種有趣方式是: 如果您有 IP 電話的 MAC 位址, 您可以在 [MAC 位址] 文字方塊中輸入該位址, 即可找出最後一次使用該手機的使用者。 接著, IP 電話清點報告會傳回與該手機通訊的使用者 SIP 位址 (在其他專案中)。 或者, 您也可以輸入使用者 SIP 位址 (在 [使用者 URI 首碼] 方塊中), 找出該使用者所使用的所有電話。
  
## <a name="filters"></a>濾鏡

篩選提供一種方式, 可讓您傳回更精細設定目標的資料集, 或以不同方式查看傳回的資料。 例如, IP 電話清點可讓您只查看特定公司生產的電話, 甚至是那些手機的特定版本。 您也可以選擇分組資料的方式。 在這種情況下, 登記會依小時、日、周或月進行分組。
  
下表列出您可搭配 IP 電話清點報告使用的篩選準則。
  
**IP 電話清點報表篩選**

|**名稱**|**說明**|
|:-----|:-----|
|**從** <br/> |時間範圍的開始日期/時間。 若要依時間查看資料, 請輸入 [開始日期] 和 [時間], 如下所示:  <br/> 7/7/2015 1:00 PM  <br/> 如果您沒有輸入開始時間, 報告會在指定日期自動于12:00 點開始。 若要依天查看資料, 只需輸入日期:  <br/> 7/7/2015  <br/> 若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):  <br/> 7/3/2015  <br/> 周數總是從星期日到星期六執行。  <br/> |
|**自** <br/> |時間範圍的結束日期/時間。 若要依時間查看資料, 請輸入 [結束日期] 和 [時間], 如下所示:  <br/> 7/7/2015 1:00 PM  <br/> 如果您沒有輸入結束時間, 報告會在指定日期自動結束于12:00。 若要依天查看資料, 只需輸入日期:  <br/> 7/7/2015  <br/> 若要依周或依月查看, 請在您要查看的周或月份中, 輸入您要查看的日期 (不需要輸入周或月的第一天):  <br/> 7/3/2015  <br/> 周數總是從星期日到星期六執行。  <br/> |
|**製造商** <br/> |製造 IP 電話的公司名稱。 此篩選的值會根據目前在資料庫中的 IP 電話自動填入。  <br/> |
|**硬體版本** <br/> |IP 電話的版本號碼;使用製造商和硬體版本篩選, 您可以唯一識別特定類型的手機。 此篩選的值會根據目前在資料庫中的 IP 電話自動填入。  <br/> |
|**使用者代理程式** <br/> |IP 電話使用的軟體識別碼。 此篩選的值會根據目前資料庫中的 IP 電話自動填入。  <br/> |
|**MAC 位址** <br/> |IP 電話上網路介面的唯一識別碼。 媒體存取控制 (MAC) 位址通常是在撥打電話並固定在裝置硬體中時指派。  <br/> 若要搜尋與特定 MAC 位址相關的記錄, 只要輸入該位址即可。 例如：  <br/> 00-08-5D-16-16-48  <br/> 您必須輸入完整的位址。 部分位址 (例如 00-08-5D) 不會傳回任何資料。  <br/> |
|**天數前的最後一個活動** <br/> | 選取下列其中一個值: <br/>  同時 <br/>  第 <br/>  20 <br/>  為期 <br/> |
|**上次登出時間 (天之前)** <br/> | 選取下列其中一個值: <br/>  同時 <br/>  第 <br/>  20 <br/>  為期 <br/> |
|**使用者 URI 首碼** <br/> |使用 IP 電話的使用者的 SIP 位址。  <br/> |
   
## <a name="metrics"></a>指標

下表列出 IP 電話清點報告中提供的資訊。
  
**IP 電話清點報告度量單位**

|**名稱**|**您可以針對此專案進行排序嗎？**|**說明**|
|:-----|:-----|:-----|
|**製造商** <br/> |是的  <br/> |製造 IP 電話的公司名稱。  <br/> |
|**硬體版本** <br/> |是的  <br/> |IP 電話的版本號碼。  <br/> |
|**MAC 位址** <br/> |是的  <br/> |IP 電話上網路介面的唯一識別碼。 MAC 位址通常是在撥打電話並將它硬連接至裝置硬體時指派。  <br/> |
|**使用者 URI** <br/> |是的  <br/> |使用 IP 電話的使用者的 SIP 位址。  <br/> |
|**使用者代理程式** <br/> |是的  <br/> |IP 電話使用的軟體識別碼。  <br/> |
|**上次登入時間** <br/> |是的  <br/> |IP 電話上次登入商務用 Skype Server 的日期和時間。  <br/> |
|**上次登出時間** <br/> |是的  <br/> |IP 電話上次從商務用 Skype Server 登出的日期和時間。  <br/> |
|**上次活動** <br/> |是的  <br/> |上次使用 IP 電話的日期和時間。  <br/> |
   

