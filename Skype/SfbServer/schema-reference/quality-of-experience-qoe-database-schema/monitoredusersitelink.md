---
title: MonitoredUserSiteLink 表格
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表格是支援的表格。 每筆記錄代表兩個使用者網站間的一個連結。
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806353"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表格
 
MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主要、外部  <br/> |從 [UserSite 表格](usersite.md)中參照。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主要、外部  <br/> |[UserSite 表格](usersite.md)中的參照。  <br/> |
   

