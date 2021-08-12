---
title: 會議表格
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 會議表格是一種支援資料表，其中的每一項記錄都代表一個會議或對等工作階段。
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309152"
---
# <a name="conference-table"></a>會議表格
 
會議表格是一種支援資料表，其中的每一項記錄都代表一個會議或對等工作階段。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |主要  <br/> |用於識別此會議記錄的唯一號碼。  <br/> |
|**ConfURI** <br/> |Nvarchar (450)   <br/> |unique  <br/> |會議 URI (若為會議)，或 DialogID (若為點對點工作階段)。  <br/> |
|**總和檢查碼** <br/> |int  <br/> |index  <br/> |會議 URI 的總和檢查碼。僅限內部使用。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||僅限內部使用。  <br/> |
   

