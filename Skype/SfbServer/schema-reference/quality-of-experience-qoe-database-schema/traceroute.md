---
title: TraceRoute 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表格包含來自呼叫的路由資訊。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 8a4ca952bb2b6ced61f4b1aae6745a5e1b68d417
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840915"
---
# <a name="traceroute-table"></a>TraceRoute 表格
 
TraceRoute 表格包含來自呼叫的路由資訊。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要，外部  <br/> |通話的開始日期與時間。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要、外部  <br/> |唯一識別碼，用來區分可能在相同日期和同一時間開始的多個通話。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要，外部  <br/> |代表通話中使用的影片線條類型。 允許的值為：  <br/> 0-音訊  <br/> 1-影片  <br/> 2-全景影片  <br/> 3-應用程式/桌面共用  <br/> |
|**FromCaller** <br/> |位  <br/> |主要  <br/> |撥出電話的端點。  <br/> |
|**跳** <br/> |int  <br/> ||網路躍點/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Foreign  <br/> |IP 位址的唯一識別碼。 IP 位址資訊會儲存在 [IPAddress 表格](ipaddress.md)中。  <br/> |
|**RTT** <br/> |int  <br/> ||往返時間。 「往返時間」會測量語音資料包到達目的地所需的時間長度，然後傳回收到的通知。  <br/> |
   

