---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398607"
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
   

