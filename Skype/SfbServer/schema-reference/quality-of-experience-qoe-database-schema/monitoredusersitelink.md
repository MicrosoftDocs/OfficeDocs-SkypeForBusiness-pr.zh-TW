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
description: MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。
ms.openlocfilehash: 7c7edea00fdd680ece091d06aa7528fb0dc7fe25d5b5b4fa126c37c48b3ee81d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321605"
---
# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink 表格
 
MonitoredUserSiteLink 表格是一種支援資料表，其中的每一項記錄都代表兩個使用者網站間的連結。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |主要、外部  <br/> |從 [UserSite 表格](usersite.md)中參照。  <br/> |
|**UserSite2Key** <br/> |int  <br/> |主要、外部  <br/> |[UserSite 表格](usersite.md)中的參照。  <br/> |
   

