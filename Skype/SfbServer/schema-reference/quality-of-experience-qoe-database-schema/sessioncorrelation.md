---
title: SessionCorrelation 表格
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 資料表是支援資料表。 每筆記錄代表一個 CorrelationID，用於關聯多個會話。
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805741"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表格
 
SessionCorrelation 資料表是支援資料表。 每筆記錄代表一個 CorrelationID，用於關聯多個會話。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**求和** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |首選  <br/> |識別這個 A/V 會議伺服器的唯一號碼。  <br/> |
|**Id** <br/> |Nvarchar （256）  <br/> |唯一  <br/> |關聯的會話將具有相同的關聯 ID。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |僅供內部使用。  <br/> |
   

