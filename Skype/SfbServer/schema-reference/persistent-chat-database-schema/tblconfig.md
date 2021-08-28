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
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
ms.openlocfilehash: 8cf1fc53087d3fc786ac47e848a21dbd2a8f5549
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595305"
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
   

