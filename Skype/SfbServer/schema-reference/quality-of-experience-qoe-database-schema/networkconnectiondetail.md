---
title: NetworkConnectionDetail 表格
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: d41b89ce85ee365d883c2224f2da29fca3cab926
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394705"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表格
 
NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |主要  <br/> |網路連線類型的唯一識別碼。  <br/> |
|**NetworkConnectionDetail** <br/> |Varchar (256)   <br/> |Unique  <br/> |對應至 NetworkConnectionDetailKey 的網路連線類型。 允許的值為：  <br/> 0--有線  <br/> 1--WiFi  <br/> 2--乙太網路  <br/> 3--MobileBB  <br/> 4--其他  <br/> 5--Tunnel  <br/> |
   

