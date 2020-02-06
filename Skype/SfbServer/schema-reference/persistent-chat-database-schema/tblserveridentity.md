---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812271"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|serverID  <br/> |int，not null  <br/> |[伺服器識別碼]。 與中央管理存放區中的實例識別碼相對應。  <br/> |
|serverAddress  <br/> |Nvarchar （256），not null  <br/> |使用 Windows Communication Foundation 位址的伺服器位址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |頻道伺服器更新此列以提供其所執行證據的最晚時間。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|serverID  <br/> |主鍵。  <br/> |
   

