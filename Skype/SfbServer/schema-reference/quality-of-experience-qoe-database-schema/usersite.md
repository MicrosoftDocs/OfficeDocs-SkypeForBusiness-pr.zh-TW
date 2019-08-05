---
title: UserSite 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192616"
---
# <a name="usersite-table"></a>UserSite 表格
 
UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |首選  <br/> |識別使用者網站的唯一號碼。  <br/> |
|**UserSiteName** <br/> |Nvarchar  <br/> |唯一  <br/> |使用者網站的名稱。  <br/> |
|**RegionKey** <br/> |int  <br/> |外  <br/> |從[Region 資料表](region.md)中參照。  <br/> |
   

