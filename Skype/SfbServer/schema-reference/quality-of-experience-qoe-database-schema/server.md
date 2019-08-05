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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 伺服器資料表是支援資料表。 每個記錄代表一台伺服器。
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192635"
---
# <a name="server-table"></a>Server 表格
 
伺服器資料表是支援資料表。 每個記錄代表一台伺服器。 
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |首選  <br/> |識別伺服器的唯一號碼。  <br/> |
|**FQDNOrIP** <br/> |Nvarchar (256)  <br/> |index  <br/> |MAC 位址字串。  <br/> |
|**ServerType** <br/> |int  <br/> |外  <br/> |1: 中繼伺服器  <br/> 2: a/V 會議 Server16394: A/V 邊緣 service32769: 閘道  <br/> |
|**PoolName** <br/> |Nvarchar (512)  <br/> ||伺服器所屬的池。 僅適用于 A/V 會議伺服器。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅供內部使用。  <br/> |
   

