---
title: Phones 表格
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: '[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。'
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815001"
---
# <a name="phones-table"></a>Phones 表格
 
[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |首選  <br/> |標識此手機的唯一號碼。  <br/> |
|**PhoneUri** <br/> |Nvarchar （450）  <br/> | <br/> |電話號碼。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||時間戳記（僅供內部使用）。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

