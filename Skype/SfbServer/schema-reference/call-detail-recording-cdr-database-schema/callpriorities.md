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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 資料表是一個靜態資料表，可儲存可能的通話優先順序清單，例如「緊急」、「緊急」或「標準」。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815441"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallPriorities 表格
 
CallPriorities 資料表是一個靜態資料表，可儲存可能的通話優先順序清單，例如「緊急」、「緊急」或「標準」。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |首選  <br/> ||
|**優先順序** <br/> |Nvarchar （256）  <br/> || 允許的值： <br/>  0-未知 <br/>  1-非緊急 <br/>  2-標準 <br/>  3-緊急 <br/>  4-緊急 <br/> |
   

