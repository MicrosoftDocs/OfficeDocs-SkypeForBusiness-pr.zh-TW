---
title: 商務用 Skype Server 2015 中的 DeRegisterType 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表格是一個靜態表格，可儲存可能的使用者取消註冊類型清單，例如「用戶端初始化」、「註冊到期」或「用戶端已停止回應」。
ms.openlocfilehash: f369416a15f0b1c024dd70fbe97042193940f669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743989"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 DeRegisterType 表格
 
DeRegisterType 表格是一個靜態表格，可儲存可能的使用者取消註冊類型清單，例如「用戶端初始化」、「註冊到期」或「用戶端已停止回應」。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |主要  <br/> ||
|**DeRegisterReason** <br/> |Nvarchar (256)   <br/> || 允許的值： <br/>  0 -- 不明 <br/>  1 -- 由用戶端起始取消註冊 <br/>  2 -- 註冊到期 <br/>  3-用戶端已崩潰 <br/>  4 -- 使用者屬性變更 <br/>  5-偏好的註冊機構已變更 <br/>  6 -- 舊版用戶端處於生存模式 <br/> |
   

