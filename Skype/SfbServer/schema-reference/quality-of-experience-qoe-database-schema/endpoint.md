---
title: Endpoint 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 端點資料表是一個支援資料表, 可儲存已參與在資料庫中記錄會話之端點的相關資訊。 資料表中的每一筆記錄代表一個端點。
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192675"
---
# <a name="endpoint-table"></a>Endpoint 表格
 
端點資料表是一個支援資料表, 可儲存已參與在資料庫中記錄會話之端點的相關資訊。 資料表中的每一筆記錄代表一個端點。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |首選  <br/> |標識此端點的唯一號碼。  <br/> |
|**名稱** <br/> |Nvarchar (256)  <br/> |唯一  <br/> |端點名稱。  <br/> |
|**OS** <br/> |Nvarchar  <br/> | <br/> |端點的作業系統 (OS)。  <br/> |
|**CPUName** <br/> |Nvarchar  <br/> ||端點的 CPU 名稱。  <br/> |
|**CPUNumberOfCores** <br/> |Smallint  <br/> ||端點的 CPU 核心數。  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||端點的 CPU 處理器速度。  <br/> |
|**VirtualizationFlag** <br/> |Tinyint  <br/> || 表示系統是否正在虛擬化環境中執行的位標誌: <br/>  0x0000-無 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-虛擬電腦 <br/>  0x0008-Xen 電腦 <br/> |
   

