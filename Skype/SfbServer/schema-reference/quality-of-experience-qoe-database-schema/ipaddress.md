---
title: IPAddress 表格
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802773"
---
# <a name="ipaddress-table"></a>IPAddress 表格
 
IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |主要  <br/> |指定之 IP 位址的唯一識別碼。  <br/> |
|**IPAddress** <br/> |Varchar (50)   <br/> |Unique  <br/> |唯一的 IP 位址 (例如，189.168.1.1) 會對應至 IpAddressKey。 這可以是 IPv4 或 IPv6 位址。  <br/> |
   

