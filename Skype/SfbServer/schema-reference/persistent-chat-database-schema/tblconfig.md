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
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809733"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含一些持久聊天伺服器不支援的設定，一列。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)，非 null  <br/> |包含「集區」。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |設定內容。  <br/> |
|configPoolID  <br/> |GUID，非 null  <br/> |資料庫執行個體的唯一識別碼。  <br/> |
   
**Key**

|**欄**|**描述**|
|:-----|:-----|
|configLabel  <br/> |主索引鍵。  <br/> |
   

