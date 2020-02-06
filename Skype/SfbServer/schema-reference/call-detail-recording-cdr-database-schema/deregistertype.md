---
title: 商務用 Skype Server 2015 中的 DeRegisterType 表格
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 資料表是一個靜態資料表，它儲存可能的使用者取消註冊類型（例如「用戶端已啟動」、「註冊已過期」或「用戶端已停止回應」）清單。
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815291"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 DeRegisterType 表格
 
DeRegisterType 資料表是一個靜態資料表，它儲存可能的使用者取消註冊類型（例如「用戶端已啟動」、「註冊已過期」或「用戶端已停止回應」）清單。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |首選  <br/> ||
|**DeRegisterReason** <br/> |Nvarchar （256）  <br/> || 允許的值： <br/>  0--未知 <br/>  1--用戶端啟動取消註冊 <br/>  2--註冊已過期 <br/>  3-用戶端發生故障 <br/>  4--使用者屬性已變更 <br/>  5-首選的註冊機構已變更 <br/>  6--生存模式中的舊版用戶端 <br/> |
   

