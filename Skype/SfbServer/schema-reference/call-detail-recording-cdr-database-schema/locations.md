---
title: 商務用 Skype Server 中的位置表格2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: 每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821513"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 中的位置表格2015
 
每筆記錄代表緊急通話中參照的一個位置，例如 E9-1-1 通話。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。 <br/> |
|**位置** <br/> |Nvarchar (max)   <br/> ||緊急電話的位置。  <br/> |
   

