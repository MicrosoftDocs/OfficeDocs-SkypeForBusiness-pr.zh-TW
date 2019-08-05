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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含部分持續聊天伺服器不支援的設定 (在單一列中)。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192744"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig 包含部分持續聊天伺服器不支援的設定 (在單一列中)。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|configLabel  <br/> |Nvarchar (255), not null  <br/> |包含 "pool"。  <br/> |
|configContent  <br/> |Nvarchar (max)  <br/> |配置內容。  <br/> |
|configPoolID  <br/> |GUID, 不是 null  <br/> |資料庫實例的唯一識別碼。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|configLabel  <br/> |主鍵。  <br/> |
   

