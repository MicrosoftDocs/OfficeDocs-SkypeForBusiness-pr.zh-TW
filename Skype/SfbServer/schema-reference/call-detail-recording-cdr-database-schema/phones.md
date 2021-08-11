---
title: 電話表格
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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 電話系表是支援的表格。 資料表中的每一筆記錄都儲存在包含資料庫中記錄的 VoIP 通話中相關的一個電話號碼相關資訊。
ms.openlocfilehash: 938e00267f5f356c646d363033ef9a8917b910261f873637c0f6b3a6b9ff8742
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329457"
---
# <a name="phones-table"></a>電話表格
 
電話系表是支援的表格。 資料表中的每一筆記錄都儲存在包含資料庫中記錄的 VoIP 通話中相關的一個電話號碼相關資訊。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |主要  <br/> |用於識別此電話的唯一號碼。  <br/> |
|**PhoneUri** <br/> |Nvarchar (450)   <br/> | <br/> |電話號碼。  <br/> |
|**NextUpdateTS** <br/> |Datetime  <br/> ||僅供內部使用) 的時間戳記 (。  <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

