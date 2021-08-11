---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278351"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)，非 null  <br/> |包含「集區」。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |設定內容。  <br/> |
|configPoolID  <br/> |GUID，非 null  <br/> |資料庫執行個體的唯一識別碼。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|configLabel  <br/> |主索引鍵。  <br/> |
   

