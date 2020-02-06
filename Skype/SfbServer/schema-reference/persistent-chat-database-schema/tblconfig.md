---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含部分持續聊天伺服器不支援的設定（在單一列中）。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814621"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含部分持續聊天伺服器不支援的設定（在單一列中）。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|configLabel  <br/> |Nvarchar （255），not null  <br/> |包含 "pool"。  <br/> |
|configContent  <br/> |Nvarchar （max）  <br/> |配置內容。  <br/> |
|configPoolID  <br/> |GUID，不是 null  <br/> |資料庫實例的唯一識別碼。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|configLabel  <br/> |主鍵。  <br/> |
   

