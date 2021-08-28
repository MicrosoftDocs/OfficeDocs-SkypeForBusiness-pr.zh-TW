---
title: 伺服器表格
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
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援的表格。 每筆記錄代表一部伺服器。
ms.openlocfilehash: 5e8173236122c6127c9e741700a5f0200c311eee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593357"
---
# <a name="server-table"></a>伺服器表格
 
伺服器資料表是支援的表格。 每筆記錄代表一部伺服器。 
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |主要  <br/> |用於識別伺服器的唯一號碼。  <br/> |
|**FQDNOrIP** <br/> |Nvarchar (256)   <br/> |index  <br/> |MAC 位址字串。  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1：轉送伺服器  <br/> 2： A/V 會議 Server16394： A/V Edge service32769：閘道  <br/> |
|**PoolName** <br/> |Nvarchar (512)   <br/> ||伺服器所屬的集區。 僅適用于 A/V 會議伺服器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅限內部使用。  <br/> |
   

