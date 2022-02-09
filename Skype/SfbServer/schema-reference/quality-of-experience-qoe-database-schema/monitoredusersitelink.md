---
title: MonitoredUserSiteLink 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399527"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表格
 
MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主要、外部  <br/> |從 [UserSite 表格](usersite.md)中參照。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主要、外部  <br/> |[UserSite 表格](usersite.md)中的參照。  <br/> |
   

