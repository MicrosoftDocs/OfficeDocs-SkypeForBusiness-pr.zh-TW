---
title: SessionCorrelation 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表格是支援的表格。 每筆記錄代表一個用於關聯多個會話的 CorrelationID。
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314419"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 表格
 
SessionCorrelation 表格是支援的表格。 每筆記錄代表一個用於關聯多個會話的 CorrelationID。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**總和檢查碼** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |主要  <br/> |用於識別此 A/V 會議伺服器的唯一號碼。  <br/> |
|**CorrelationID** <br/> |Nvarchar (256)   <br/> |Unique  <br/> |關聯的會話會有相同的相互關聯識別碼。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |僅限內部使用。  <br/> |
   

