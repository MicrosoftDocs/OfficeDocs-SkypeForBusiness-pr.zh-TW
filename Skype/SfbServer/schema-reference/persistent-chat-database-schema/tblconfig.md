---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
ms.openlocfilehash: 344922f4ffb1cf172c154117c95491558f8e8905
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767361"
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
   

