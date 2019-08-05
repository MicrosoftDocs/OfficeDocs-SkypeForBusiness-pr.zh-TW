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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 資料表是支援資料表。 每筆記錄代表一個 CorrelationID, 用於關聯多個會話。
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192630"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表格
 
SessionCorrelation 資料表是支援資料表。 每筆記錄代表一個 CorrelationID, 用於關聯多個會話。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**求和** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |首選  <br/> |識別這個 A/V 會議伺服器的唯一號碼。  <br/> |
|**Id** <br/> |Nvarchar (256)  <br/> |唯一  <br/> |關聯的會話將具有相同的關聯 ID。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |僅供內部使用。  <br/> |
   

