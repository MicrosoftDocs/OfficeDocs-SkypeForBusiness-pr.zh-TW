---
title: 商務用 Skype Server 2015 中的 ClientVersions 表格
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386322"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ClientVersions 表格
 
ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |主要  <br/> |用於識別此用戶端類型及版本的唯一號碼。  <br/> |
|**版本** <br/> |**Nvarchar (256)** <br/> ||版本名稱。  <br/> |
|**ClientType** <br/> |int  <br/> ||指出工作階段所使用的用戶端類型。 如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。 <br/> 此欄位是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

