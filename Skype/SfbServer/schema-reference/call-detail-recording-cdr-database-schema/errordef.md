---
title: 商務用 Skype Server 2015 中的 ErrorDef 表格
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表會儲存可能發生的每一種錯誤類型的相關資訊。 每個記錄是一種錯誤類型。
ms.openlocfilehash: c725baeeefa750d8feded45483c74ec849b7842a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858190"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorDef 表格
 
ErrorDef 表會儲存可能發生的每一種錯誤類型的相關資訊。 每個記錄是一種錯誤類型。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |主要  <br/> |用來識別這種錯誤類型的唯一識別碼號碼。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |與此錯誤相關聯的標準 SIP 回應碼。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 診斷識別碼。  <br/> |
|**CallTypeId** <br/> |臨界值  <br/> |Foreign  <br/> |通話的類型。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的 CallType 表格](calltype.md)。 <br/> |
|**RequestType** <br/> |Varbinary (33)   <br/> | <br/> |失敗的要求類型。  <br/> 您可以使用下列語法將此資料轉換成文字格式：  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |Varbinary (257)   <br/> | <br/> |失敗之要求的內容類型。  <br/> 您可以使用此 syntaxt 將此資料轉換成文字格式：  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

