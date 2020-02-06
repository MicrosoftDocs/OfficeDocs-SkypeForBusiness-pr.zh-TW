---
title: TraceRoute 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表格包含來自呼叫的路由資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805111"
---
# <a name="traceroute-table"></a>TraceRoute 資料表
 
TraceRoute 表格包含來自呼叫的路由資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要、外部  <br/> |通話的開始日期和時間。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要、外部  <br/> |唯一識別碼，用來區分可能已在相同日期和同一時間開始的多個通話。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要、外部  <br/> |代表通話中使用的影片線條類型。 允許的值為：  <br/> 0-音訊  <br/> 1-影片  <br/> 2-全景影片  <br/> 3-應用程式/桌面共用  <br/> |
|**FromCaller** <br/> |稍微  <br/> |首選  <br/> |放置通話的端點。  <br/> |
|**中繼站** <br/> |int  <br/> ||Network hop/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |外  <br/> |IP 位址的唯一識別碼。 IP 位址資訊會儲存在 [ [IPAddress] 資料表](ipaddress.md)中。  <br/> |
|**RTT** <br/> |int  <br/> ||往返時間。 往返時間會測量語音資料包達到目的地所需的時間長度，然後傳回接收的通知。  <br/> |
   

