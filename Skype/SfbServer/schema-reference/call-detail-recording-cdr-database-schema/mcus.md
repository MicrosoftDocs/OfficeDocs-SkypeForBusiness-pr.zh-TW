---
title: 商務用 Skype Server 2015 中的 Mcus 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 資料表是支援資料表。 每筆記錄儲存一個會議服務的相關資訊。 這些可能包括 IM 會議服務和電話會議服務 (在前端伺服器上以進程的方式執行), 以及網路會議服務和 A/V 會議服務。
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192830"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 Mcus 表格
 
Mcus 資料表是支援資料表。 每筆記錄儲存一個會議服務的相關資訊。 這些可能包括 IM 會議服務和電話會議服務 (在前端伺服器上以進程的方式執行), 以及網路會議服務和 A/V 會議服務。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |首選  <br/> |標識此會議服務器的唯一號碼。  <br/> |
|**McuUri** <br/> |Nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 外 <br/> |會議服務器類型, 例如會議: 聊天 (適用于 Im) 或會議: 音訊影片。 如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
   

