---
title: 商務用 Skype Server 2015 中的 CallType 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 資料表是一個靜態資料表, 可儲存可能的通話類型清單。
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192903"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallType 表格
 
CallType 資料表是一個靜態資料表, 可儲存可能的通話類型清單。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |首選  <br/> ||
|**CallType** <br/> |Nvarchar  <br/> || 允許的值: <br/>  0--未知 <br/>  1-立即訊息 <br/>  2--應用程式共用 <br/>  3--音訊 <br/>  4-音訊和影片 <br/>  5-檔案傳輸 <br/> |
   

