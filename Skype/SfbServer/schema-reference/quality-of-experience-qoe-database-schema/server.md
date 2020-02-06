---
title: Server 表格
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援資料表。 每個記錄代表一台伺服器。
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806131"
---
# <a name="server-table"></a>Server 表格
 
伺服器資料表是支援資料表。 每個記錄代表一台伺服器。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |首選  <br/> |識別伺服器的唯一號碼。  <br/> |
|**FQDNOrIP** <br/> |Nvarchar （256）  <br/> |index  <br/> |MAC 位址字串。  <br/> |
|**ServerType** <br/> |int  <br/> |外  <br/> |1：中繼伺服器  <br/> 2： a/V 會議 Server16394： A/V 邊緣 service32769：閘道  <br/> |
|**PoolName** <br/> |Nvarchar （512）  <br/> ||伺服器所屬的池。 僅適用于 A/V 會議伺服器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅供內部使用。  <br/> |
   

