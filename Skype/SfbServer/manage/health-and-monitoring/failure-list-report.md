---
title: 商務用 Skype Server 中的 [失敗清單] 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '摘要: 瞭解商務用 Skype 伺服器中的 [失敗清單] 報告。'
ms.openlocfilehash: 72637863d7a15d26ea997de8a9c3526279afc57f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193738"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>商務用 Skype Server 中的 [失敗清單] 報告 
 
**摘要:** 瞭解商務用 Skype Server 中的 [失敗清單] 報告。
  
[失敗清單] 報告會提供參與對等無法進行對等或會議會話的個別參與者的相關資訊。 此資訊包含遇到問題之使用者的 URI, 以及與失敗相關聯的 SIP 回應程式碼與診斷 ID。
  
## <a name="accessing-the-failure-list-report"></a>存取失敗清單報告

若要存取 [失敗清單] 報告, 請按一下 [商務用 Skype 伺服器] 的 [[失敗] 發佈報告中](failure-distribution-report.md)的任何一個度量單位:
  
- 常見的診斷原因 (會話)
    
- 熱門形式 (會話)
    
- 頂層池 (會話)
    
- 熱門來源 (會話)
    
- Top 元件 (會話)
    
- 使用者的最上層 (會話)
    
- 使用者的最上層 (會話)
    
- 使用者代理程式 (會話) 的頂端
    
在 [失敗清單] 報告中, 您可以透過按一下點對點工作階段的會話詳細資料指標,[在商務用 Skype Server 中存取點對點工作階段詳細資料包告](peer-to-peer-session-detail-report.md)。 您也可以按一下會議的會議指標, 以存取會議詳細資料包告。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>充分利用 [失敗清單] 報告

在 [失敗清單] 報告中, 您只要將滑鼠放在該值上, 就能查看每個回應代碼或每個診斷 ID 的描述。 例如, 如果您將滑鼠放在診斷 ID 7025 上, 您會看到下列顯示在工具提示中:
  
為使用者建立媒體時發生內部伺服器錯誤。
  
請務必注意, [失敗清單] 報告不會提供直接檢索至少參與一個失敗會話之所有使用者清單的簡單方法, 也不會提供判斷哪些使用者最常參與失敗的方法。課時. (一件事, 失敗清單報告沒有篩選功能)。不過, 如果您匯出資料, 然後將它轉換成逗號分隔值檔案, 您可以使用 Windows PowerShell 來尋找問題等問題的答案。 例如, 假設您將資料儲存至。名為 C:\Data\Failure_List.csv. 的 CSV 檔案 根據儲存在該檔案中的資料, 此命令會列出至少有一個失敗的會話中所涉及的所有使用者: 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

該命令會傳回如下所示的清單:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

這兩個命令會傳回每位使用者所涉及的失敗會話總數:
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

這樣會傳回如下所示的資料:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>濾鏡

無。 您無法篩選失敗清單報告。
  
## <a name="metrics"></a>指標

下表列出每個失敗的通話在失敗清單報告中所提供的資訊。
  
**失敗清單報告度量單位**

|**名稱**|**您可以針對此專案進行排序嗎？**|**說明**|
|:-----|:-----|:-----|
|**報告時間** <br/> |不  <br/> |記錄報告的日期和時間。  <br/> |
|**徵求** <br/> |不  <br/> |失敗的 SIP 要求類型。 例如, [邀請] 或 [再見]。  <br/> |
|**回應代碼** <br/> |不  <br/> |在會議失敗時傳送 SIP 回應代碼。  <br/> |
|**診斷識別碼** <br/> |不  <br/> |附加至 SIP 訊息的唯一識別碼 (ms diagnostics 標頭形式), 通常可在疑難排解錯誤中提供有用的資訊。  <br/> |
|**加入成本時間 (毫秒)** <br/> |不  <br/> |使用者加入會議所需的時間長度 (以毫秒為單位)。  <br/> |
|**從使用者** <br/> |不  <br/> |啟動通話的使用者的 SIP 位址。  <br/> |
|**從使用者代理程式** <br/> |不  <br/> |啟動通話之使用者的端點所使用的軟體。  <br/> |
|**給使用者** <br/> |不  <br/> |呼叫的使用者的 SIP 位址。  <br/> |
   

