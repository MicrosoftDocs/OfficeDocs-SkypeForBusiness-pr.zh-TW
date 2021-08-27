---
title: Dialog 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。
ms.openlocfilehash: 0310845ada3b86346ccc6b410a5c7539b16689f3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603722"
---
# <a name="dialog-table"></a>Dialog 表格
 
Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |卓越品質 (Quality of Excellence, QoE) 代理程式從發話者或受話者收到第一份報告的時間。其會與 SessionSeq 搭配使用，專門用於識別工作階段。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |當工作階段的 ConferenceDateTime 相同時，用來區分工作階段的序號。  <br/> |
|**DialogID** <br/> |Varchar (256)   <br/> ||全域唯一的對話方塊 ID。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |對話方塊 ID 的總和檢查碼。  <br/> |
   

