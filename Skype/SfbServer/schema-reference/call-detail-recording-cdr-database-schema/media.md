---
title: 媒體資料表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每個記錄代表點對點工作階段中所使用的一種媒體類型。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815041"
---
# <a name="media-table"></a>媒體資料表格
 
每個記錄代表點對點工作階段中所使用的一種媒體類型。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。
  
> [!NOTE]
> 媒體資料表不應該用來計算會話的媒體持續時間。 此表格包含會話中媒體交換的信號詳細資料。 媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在 sessionee 接受會話之後才會啟動。 [EndTime] 通常代表這個會話的結束時間。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**MediaId** <br/> |Tinyint  <br/> |主要、外部  <br/> |識別這個媒體類型的唯一號碼。 如需詳細資訊，請參閱[MediaList 資料表](medialist.md)。 <br/> |
|**開始** <br/> |datetime  <br/> |首選  <br/> |這是傳送媒體要求的時間，而不是真正的媒體啟動時間。 **StartTime**包含會話設定時間。 <br/> |
|**EndTime** <br/> |datetime  <br/> ||這是會話的結束時間。  <br/> |
   

