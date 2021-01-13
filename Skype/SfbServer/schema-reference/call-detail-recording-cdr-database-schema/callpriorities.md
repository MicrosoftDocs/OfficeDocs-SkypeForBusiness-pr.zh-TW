---
title: 商務用 Skype Server 2015 中的 CallPriorities 表格
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表格是一個靜態表格，它會儲存可能通話優先順序的清單，例如 "緊急"、"緊急" 或 "normal"。
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813433"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CallPriorities 表格
 
CallPriorities 表格是一個靜態表格，它會儲存可能通話優先順序的清單，例如 "緊急"、"緊急" 或 "normal"。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |Tinyint  <br/> |主要  <br/> ||
|**優先順序** <br/> |Nvarchar (256)   <br/> || 允許的值： <br/>  0 - 未知 <br/>  1-非緊急 <br/>  2 - 一般 <br/>  3 - 急 <br/>  4 - 緊急 <br/> |
   

