---
title: 商務用 Skype Server 2015 中的 ClientVersions 表格
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 資料表是一個支援資料表，可儲存已參與在資料庫中記錄的會話的各種用戶端類型和版本清單。 資料表中的每一筆記錄代表一個用戶端版本。
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815401"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ClientVersions 表格
 
ClientVersions 資料表是一個支援資料表，可儲存已參與在資料庫中記錄的會話的各種用戶端類型和版本清單。 資料表中的每一筆記錄代表一個用戶端版本。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |首選  <br/> |標識此用戶端類型與版本的唯一號碼。  <br/> |
|**版本** <br/> |**Nvarchar （256）** <br/> ||版本名稱。  <br/> |
|**ClientType** <br/> |int  <br/> ||指定會話中使用的用戶端類型。 如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。 <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

