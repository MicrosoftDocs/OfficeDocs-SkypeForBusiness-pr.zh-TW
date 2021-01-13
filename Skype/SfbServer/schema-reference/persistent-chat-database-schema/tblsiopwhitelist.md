---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可與節點相關聯的註冊增益集清單。
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831483"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList 是可與節點相關聯的註冊增益集清單。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID，非 null  <br/> |增益集的 GUID。  <br/> |
|siopName  <br/> |nvarchar (50)，非 null  <br/> |增益集的顯示名稱。  <br/> |
|siopUrl  <br/> |nvarchar (255)，非 null  <br/> |增益集的 URL。  <br/> |
   
**Key**

|**欄**|**描述**|
|:-----|:-----|
|siopID  <br/> |主索引鍵。  <br/> |
   

