---
title: 商務用 Skype Server 的失敗清單報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 摘要：瞭解商務用 Skype Server 中的失敗清單報告。
ms.openlocfilehash: 3943c802bd6f6bce593c8fdfafb05179252712b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582737"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>商務用 Skype Server 的失敗清單報告 
 
**摘要：** 深入瞭解商務用 Skype Server 中的失敗清單報告。
  
「失敗清單報告」會提供參與「對等」或「會議」會話失敗之人員的相關資訊。 此資訊包含發生問題之使用者的 URI，以及與失敗相關聯的 SIP 回應碼和診斷識別碼。
  
## <a name="accessing-the-failure-list-report"></a>存取失敗清單報告

若要存取失敗清單報告，請按一下 [[失敗散佈報告] 中](failure-distribution-report.md)的下列任一度量（商務用 Skype Server：
  
- 前幾名診斷原因 (工作階段)
    
- 最常見形式 (工作階段)
    
- 最常見集區 (工作階段)
    
- 最常見來源 (工作階段)
    
- 最常見元件 (工作階段)
    
- 最常見來源使用者 (工作階段)
    
- 最常見目標使用者 (工作階段)
    
- 最常見來源使用者代理程式 (工作階段)
    
在 [失敗清單] 報告中，您可以按一下點對點工作階段的會話詳細資料計量，[以存取商務用 Skype Server 中的 Peer-to-Peer 會話詳細資料包告](peer-to-peer-session-detail-report.md)。 您也可以按一下會議的會議度量來存取會議詳細資料包告。
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>讓 [失敗清單] 報告的最佳用法

在 [失敗清單] 報告中，只要將滑鼠停留在該值上，您就可以查看每個回應代碼或每個診斷識別碼的描述。 例如，如果您將滑鼠停留在診斷 ID 7025 上，您會看到工具提示中顯示下列內容：
  
為使用者建立媒體時發生內部伺服器錯誤。
  
請務必注意，失敗清單報告並未提供直接找回至少參與一則失敗之會話之所有使用者的清單，也不會提供一種方法來判斷失敗的會話中最常參與的使用者。  (一件事，失敗清單報告沒有篩選功能。 ) 不過，如果您匯出資料，然後將其轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 來找出類似問題的答案。 例如，假設您將資料儲存到名為 C:\Data\Failure_List.csv 的 .CSV 檔案中。 根據儲存在該檔案中的資料，此命令會列出至少包含一個失敗會話的所有使用者： 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

該命令會傳回類似以下的清單：
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

這兩個命令傳回每位使用者參與的失敗會話總數：
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

該命令將傳回類似下列的資料：
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>篩選

無。 您無法篩選失敗清單報告。
  
## <a name="metrics"></a>度量

下表列出每個失敗通話的失敗清單報告中提供的資訊。
  
**失敗清單報告計量**

|**名稱**|**可以排序這個項目嗎？**|**描述**|
|:-----|:-----|:-----|
|**報告時間** <br/> |否  <br/> |報告的記錄日期與時間。  <br/> |
|**請求** <br/> |否  <br/> |失敗的 SIP 要求類型。 例如，INVITE 或再見。  <br/> |
|**回應碼** <br/> |否  <br/> |會議失敗時所傳送的 SIP 回應碼。  <br/> |
|**診斷識別碼** <br/> |否  <br/> |附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。  <br/> |
|**加入成本時間 (毫秒)** <br/> |否  <br/> |使用者加入會議所需的時間長度 (（毫秒）) 。  <br/> |
|**來源使用者** <br/> |否  <br/> |撥打通話之使用者的 SIP 位址。  <br/> |
|**從使用者代理程式** <br/> |否  <br/> |起始通話之使用者端點所使用的軟體。  <br/> |
|**目標使用者** <br/> |否  <br/> |呼叫之使用者的 SIP 位址。  <br/> |
   

