---
title: UserStatistics 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表格是支援的表格。 資料表中的每一筆記錄都儲存了個別使用者對系統使用方式的相關資訊。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: d0d3fde20f7c8c94629f75ff00f310111cac16d386fc0b0373ee07b5c2a35fb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302207"
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
   

