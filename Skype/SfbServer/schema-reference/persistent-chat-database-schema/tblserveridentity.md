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
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。
ms.openlocfilehash: 1e6e70835865f2ca6ef992a879dad58011a5170c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613833"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|serverID  <br/> |int，非 null  <br/> |伺服器識別碼。 對應至中央管理存放區的實例識別碼。  <br/> |
|serverAddress  <br/> |nvarchar (256)，非 null  <br/> |使用 Windows Communication Foundation 位址的伺服器位址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |通道伺服器更新此列以證明其為執行中的最新時間。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|serverID  <br/> |主索引鍵。  <br/> |
   

