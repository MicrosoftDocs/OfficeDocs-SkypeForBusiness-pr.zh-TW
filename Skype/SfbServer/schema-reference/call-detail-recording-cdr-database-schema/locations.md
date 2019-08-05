---
title: 商務用 Skype Server 2015 中的 [位置] 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每個記錄代表緊急呼叫中的一個位置參照, 就像是 E9-1-1 通話。
ms.openlocfilehash: 28054419187b8f23348396f52ec147b06eee2136
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192840"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 [位置] 表格
 
每個記錄代表緊急呼叫中的一個位置參照, 就像是 E9-1-1 通話。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用, 可唯一識別會話。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**位置** <br/> |Nvarchar (max)  <br/> ||緊急通話的位置。  <br/> |
   

