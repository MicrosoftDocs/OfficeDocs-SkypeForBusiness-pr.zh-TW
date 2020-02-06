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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805001"
---
# <a name="usersite-table"></a>UserSite 表格
 
UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |首選  <br/> |識別使用者網站的唯一號碼。  <br/> |
|**UserSiteName** <br/> |Nvarchar  <br/> |唯一  <br/> |使用者網站的名稱。  <br/> |
|**RegionKey** <br/> |int  <br/> |外  <br/> |從[Region 資料表](region.md)中參照。  <br/> |
   

