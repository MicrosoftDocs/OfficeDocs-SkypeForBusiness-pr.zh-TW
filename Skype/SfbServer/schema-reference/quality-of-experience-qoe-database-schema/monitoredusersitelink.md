---
title: MonitoredUserSiteLink 表格
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 資料表是支援資料表。 每個記錄代表兩個使用者網站之間的一個連結。
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807791"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表格
 
MonitoredUserSiteLink 資料表是支援資料表。 每個記錄代表兩個使用者網站之間的一個連結。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主要、外部  <br/> |從[UserSite 資料表](usersite.md)中參照。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主要、外部  <br/> |從[UserSite 資料表](usersite.md)中引用。  <br/> |
   

