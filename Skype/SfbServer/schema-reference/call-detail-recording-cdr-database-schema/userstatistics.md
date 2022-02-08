---
title: UserStatistics 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表格是支援的表格。 資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 29c710f86560ff204d1e6f97794cf6760a924242
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393675"
---
# <a name="userstatistics-table"></a>UserStatistics 表格
 
UserStatistics 表格是支援的表格。 資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |主要  <br/> |用於識別此使用者的唯一號碼。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||使用者上次登入的時間。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||使用者上次組織會議的時間。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||上次使用者發生通話失敗的時間。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||使用者最後一次遇到會議召集人的呼叫失敗。  <br/> |
   

