---
title: 商務用 Skype Server 2015 中的對話方塊表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 對話方塊表格是一個支援資料表, 可儲存點對點工作階段之 DialogIDs 的相關資訊。
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192871"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的對話方塊表格
 
對話方塊表格是一個支援資料表, 可儲存點對點工作階段之 DialogIDs 的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |首選  <br/> |會話要求的時間;與 SessionIDSeq 搭配使用, 可唯一識別會話。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |首選  <br/> |識別會話的識別碼編號。 與 SessionIDTime 搭配使用, 可唯一識別會話。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校驗和。 此欄位可用來提高資料庫搜尋的速度。  <br/> |
|**ExternalId** <br/> |Varbinary (775)  <br/> | <br/> |SIP 對話方塊識別碼, 儲存為二進位。 二進位檔案的格式為:  <br/> 對話方塊; 從標籤; 到標籤  <br/> 您可以使用下列語法, 將此資料轉換成文字格式:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

