---
title: Conference 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: '[會議] 表格是支援表格。 每個記錄代表一個會議或點對點工作階段。'
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810301"
---
# <a name="conference-table"></a>Conference 表格
 
[會議] 表格是支援表格。 每個記錄代表一個會議或點對點工作階段。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |首選  <br/> |標識此會議記錄的唯一號碼。  <br/> |
|**ConfURI** <br/> |Nvarchar （450）  <br/> |唯一  <br/> |會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。  <br/> |
|**求和** <br/> |int  <br/> |index  <br/> |會議 URI 的校驗和。 這會在內部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅供內部使用。  <br/> |
   

