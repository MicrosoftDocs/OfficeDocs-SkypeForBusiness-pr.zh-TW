---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。
ms.openlocfilehash: 18fe97268f277de11740b2181235a5088807c49f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620859"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，非 null  <br/> |節點識別碼 (僅聊天室類型)。  <br/> |
|lastChatID  <br/> |bigint，非 null  <br/> |最後一個使用的交談 ID。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |主索引鍵 (處理時僅有 nodeID 已足夠)。  <br/> |
|nodeID  <br/> |在 tblNode.nodeID 表格中查閱外部索引鍵。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblChat](tblchat.md)
