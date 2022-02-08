---
title: IPAddress 表格
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 52086b456d9011730252c8c104aba46369467350
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390815"
---
# <a name="ipaddress-table"></a>IPAddress 表格
 
IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |主要  <br/> |指定之 IP 位址的唯一識別碼。  <br/> |
|**IPAddress** <br/> |Varchar (50)   <br/> |Unique  <br/> |唯一的 IP 位址 (例如，189.168.1.1) 會對應至 IpAddressKey。 這可以是 IPv4 或 IPv6 位址。  <br/> |
   

