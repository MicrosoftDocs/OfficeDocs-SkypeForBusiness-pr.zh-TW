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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: '[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。'
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192817"
---
# <a name="phones-table"></a>Phones 表格
 
[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |首選  <br/> |標識此手機的唯一號碼。  <br/> |
|**PhoneUri** <br/> |Nvarchar (450)  <br/> | <br/> |電話號碼。  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||時間戳記 (僅供內部使用)。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

