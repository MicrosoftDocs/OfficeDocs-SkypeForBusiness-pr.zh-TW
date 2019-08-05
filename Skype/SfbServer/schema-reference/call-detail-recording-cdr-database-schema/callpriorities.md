---
title: 商務用 Skype Server 2015 中的 CallPriorities 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 資料表是一個靜態資料表, 可儲存可能的通話優先順序清單, 例如「緊急」、「緊急」或「標準」。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192904"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallPriorities 表格
 
CallPriorities 資料表是一個靜態資料表, 可儲存可能的通話優先順序清單, 例如「緊急」、「緊急」或「標準」。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |首選  <br/> ||
|**優先順序** <br/> |Nvarchar (256)  <br/> || 允許的值: <br/>  0-未知 <br/>  1-非緊急 <br/>  2-標準 <br/>  3-緊急 <br/>  4-緊急 <br/> |
   

