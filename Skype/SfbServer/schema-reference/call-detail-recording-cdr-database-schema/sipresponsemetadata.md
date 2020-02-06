---
title: SIPResponseMetaData 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。 系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814891"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 資料表
 
SIPResponseMetaDataTable 包含 SIP 回應代碼清單，以及每個代碼的分類與定義。 系統會產生這些代碼，以回應影響 SIP 裝置和 SIP 通訊會話的事件;例如，回應碼403是在 SIP 裝置提出要求時產生，但伺服器會拒絕服從該要求。
  
此表格是在商務用 Skype Server 2015 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |首選  <br/> |代表 SIP 回應代碼的數值。  <br/> |
|**靜態類** <br/> |int  <br/> || 回應代碼的一般分類。 分類包括： <br/>  1-資訊回應 <br/>  2-成功回應 <br/>  3重定向回應 <br/>  4-用戶端失敗回應 <br/>  5--伺服器失敗回應 <br/>  6-全域失敗回應 <br/> |
|**說明** <br/> |Nvarchar （256）  <br/> ||SIP 回應代碼的描述。 例如，回應代碼181具有下列描述：  <br/> 呼叫正在轉寄  <br/> |
   

