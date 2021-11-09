---
title: 媒體表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: 每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。
ms.openlocfilehash: 02a11f296ec24e9f907927d93bc0fb8acb103b8a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855217"
---
# <a name="media-table"></a>媒體表格
 
每一項記錄都代表對等工作階段所用的一種媒體類型。若某階段工作使用了一種以上的媒體類型，則在表格中會呈現多個記錄。
  
> [!NOTE]
> 您不應使用媒體資料表來計算工作階段的媒體持續期間。此資料表包含工作階段中的媒體交換訊號詳細資料。媒體交換是由 INVITE 要求來執行，且 StartTime 會指出 INVITE 傳送出來的時間。邀請時間不一定表示媒體開始時間，因為只有在接受工作階段後，媒體才會開始。EndTime 通常是指此工作階段的結束時間。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**MediaId** <br/> |Tinyint  <br/> |主要，外部  <br/> |用於識別此媒體類型的唯一號碼。 如需詳細資訊，請參閱 [MediaList 表格](medialist.md) 。 <br/> |
|**StartTime** <br/> |datetime  <br/> |主要  <br/> |這是媒體要求傳送出來的時間，而不是實際的媒體開始時間。**StartTime** 會指出工作階段開始時間。<br/> |
|**EndTime** <br/> |datetime  <br/> ||這是工作階段結束時間。  <br/> |
   

