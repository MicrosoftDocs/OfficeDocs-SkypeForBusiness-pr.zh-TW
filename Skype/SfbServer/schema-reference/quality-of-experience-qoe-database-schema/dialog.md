---
title: Dialog 表格
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定（SIP）] 對話方塊。
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809531"
---
# <a name="dialog-table"></a>Dialog 表格
 
對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定（SIP）] 對話方塊。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |優質（QoE）代理程式從來電者或被叫方接收到第一個報告的時間。 與 SessionSeq 搭配使用，可唯一識別會話。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |[順序編號] 可在有相同 ConferenceDateTime 的情況下區分會話。  <br/> |
|**DialogID** <br/> |Varchar （256）  <br/> ||全域唯一的對話方塊識別碼。  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |對話方塊識別碼的校驗和。  <br/> |
   

