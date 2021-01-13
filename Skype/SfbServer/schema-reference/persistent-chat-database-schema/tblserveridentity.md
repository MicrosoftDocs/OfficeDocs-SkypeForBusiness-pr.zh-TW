---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831493"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|serverID  <br/> |int，非 null  <br/> |伺服器識別碼。 對應至中央管理存放區的實例識別碼。  <br/> |
|serverAddress  <br/> |nvarchar (256)，非 null  <br/> |使用 Windows Communication Foundation 位址的伺服器位址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |通道伺服器更新此列以證明其為執行中的最新時間。  <br/> |
   
**Key**

|**欄**|**描述**|
|:-----|:-----|
|serverID  <br/> |主索引鍵。  <br/> |
   

