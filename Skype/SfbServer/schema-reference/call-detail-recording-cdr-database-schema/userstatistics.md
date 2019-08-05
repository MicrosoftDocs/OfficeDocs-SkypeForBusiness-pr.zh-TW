---
title: UserStatistics 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 資料表是支援資料表。 資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192774"
---
# <a name="userstatistics-table"></a>UserStatistics 資料表
 
UserStatistics 資料表是支援資料表。 資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**UserId** <br/> |int  <br/> |首選  <br/> |標識此使用者的唯一號碼。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||使用者最後一次登入的時間。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||使用者最後一次組織會議的時間。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||使用者最後一次遇到通話失敗的問題。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||使用者最後一次遇到「會議召集人」通話失敗的問題。  <br/> |
   

