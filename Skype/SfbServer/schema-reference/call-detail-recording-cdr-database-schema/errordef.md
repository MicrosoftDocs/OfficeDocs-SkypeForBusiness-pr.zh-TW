---
title: 商務用 Skype Server 2015 中的 ErrorDef 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。 每一筆記錄都是一種錯誤類型。
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192864"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ErrorDef 表格
 
ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。 每一筆記錄都是一種錯誤類型。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |首選  <br/> |標識此類型錯誤的唯一識別碼編號。  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |與此錯誤相關聯的標準 SIP 回應程式碼。  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 診斷 ID。  <br/> |
|**CallTypeId** <br/> |Int  <br/> |外  <br/> |通話的類型。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](calltype.md)的 [CallType] 資料表。 <br/> |
|**RequestType** <br/> |Varbinary (33)  <br/> | <br/> |失敗的要求類型。  <br/> 您可以使用下列語法, 將此資料轉換成文字格式:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |Varbinary (257)  <br/> | <br/> |失敗之要求的內容類型。  <br/> 您可以使用此 syntaxt, 將此資料轉換成文字格式:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

