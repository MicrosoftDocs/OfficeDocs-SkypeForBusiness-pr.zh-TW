---
title: Endpoint 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。 資料表中的每一筆記錄都代表一個端點。
ms.openlocfilehash: 4085b8e22aea565054dbb03de10808712c54361e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399557"
---
# <a name="endpoint-table"></a>Endpoint 表
 
端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。 資料表中的每一筆記錄都代表一個端點。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |主要  <br/> |用於識別此端點的唯一號碼。  <br/> |
|**名稱** <br/> |Nvarchar (256)   <br/> |Unique  <br/> |端點名稱。  <br/> |
|**作業系統** <br/> |Nvarchar (128)   <br/> | <br/> |端點 (作業系統) 。  <br/> |
|**CPUName** <br/> |Nvarchar (128)   <br/> ||端點的 CPU 名稱。  <br/> |
|**CPUNumberOfCores** <br/> |Smallint  <br/> ||端點的 CPU 核心數目。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||端點的 CPU 處理器速度。  <br/> |
|**VirtualizationFlag** <br/> |Tinyint  <br/> || 指出系統是否在虛擬化環境中執行的位旗標： <br/>  0x0000-無 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虛擬 PC <br/>  0x0008-Xen 電腦 <br/> |
   

