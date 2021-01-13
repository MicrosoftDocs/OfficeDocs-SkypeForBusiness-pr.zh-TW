---
title: NetworkConnectionDetail 表格
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
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806303"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 表格
 
NetworkConnectionDetail 表會將網路連線類型對應至其他在經驗品質資料庫中使用的網路連線識別碼。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |主要  <br/> |網路連線類型的唯一識別碼。  <br/> |
|**NetworkConnectionDetail** <br/> |Varchar (256)   <br/> |Unique  <br/> |對應至 NetworkConnectionDetailKey 的網路連線類型。 允許的值為：  <br/> 0--有線  <br/> 1--WiFi  <br/> 2--乙太網路  <br/> 3--MobileBB  <br/> 4--其他  <br/> 5--隧道  <br/> |
   

