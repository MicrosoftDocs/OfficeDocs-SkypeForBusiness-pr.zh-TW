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
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192709"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|serverID  <br/> |int, not null  <br/> |[伺服器識別碼]。 與中央管理存放區中的實例識別碼相對應。  <br/> |
|serverAddress  <br/> |Nvarchar (256), not null  <br/> |使用 Windows Communication Foundation 位址的伺服器位址。  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |頻道伺服器更新此列以提供其所執行證據的最晚時間。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|serverID  <br/> |主鍵。  <br/> |
   

