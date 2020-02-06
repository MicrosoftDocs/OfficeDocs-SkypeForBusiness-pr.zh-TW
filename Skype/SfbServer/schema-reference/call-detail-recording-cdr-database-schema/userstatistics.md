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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 資料表是支援資料表。 資料表中的每一筆記錄都儲存著個別使用者使用系統的相關資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814791"
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
   

