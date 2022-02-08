---
title: SIPResponseMetaData 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。 這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。
ms.openlocfilehash: 7a0bd21ab3bae176ee80ca271bad46988f43a9d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393685"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 表格
 
SIPResponseMetaDataTable 包含 SIP 回應碼的清單，以及每個代碼的分類和定義。 這兩個代碼會在回應影響 SIP 裝置和 SIP 通訊會話的事件時產生;例如，回應碼403是在 SIP 裝置提出要求時產生，但是伺服器會謝絕該要求。
  
此表格引進商務用 Skype Server 2015。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |主要  <br/> |代表 SIP 回應碼的數值。  <br/> |
|**Class** <br/> |int  <br/> || 回應碼的一般分類。 分類包括： <br/>  1-資訊回應 <br/>  2-成功的回應 <br/>  3-重新導向回應 <br/>  4-用戶端失敗回應 <br/>  5--伺服器失敗回應 <br/>  6-全域失敗回應 <br/> |
|**描述** <br/> |Nvarchar (256)   <br/> ||SIP 回應碼的描述。 例如，回應碼181的描述如下：  <br/> 轉接來電  <br/> |
   

