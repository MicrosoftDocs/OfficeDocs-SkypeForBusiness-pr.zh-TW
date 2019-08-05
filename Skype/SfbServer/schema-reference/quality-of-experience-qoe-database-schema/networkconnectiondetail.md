---
title: NetworkConnectionDetail 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail 表格會將網路連線類型對應至在體驗資料庫的 [品質] 資料庫中的其他位置所使用的網路連接識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192654"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail 資料表
 
NetworkConnectionDetail 表格會將網路連線類型對應至在體驗資料庫的 [品質] 資料庫中的其他位置所使用的網路連接識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |首選  <br/> |網路連線類型的唯一識別碼。  <br/> |
|**NetworkConnectionDetail** <br/> |Varchar (256)  <br/> |唯一  <br/> |對應至 NetworkConnectionDetailKey 的網路連線類型。 允許的值為：  <br/> 0--有線  <br/> 1--WiFi  <br/> 2--乙太網路  <br/> 3--MobileBB  <br/> 4--其他  <br/> 5--隧道  <br/> |
   

