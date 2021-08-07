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
ms.openlocfilehash: db9405a05335974456f77d8117f9e3f64e9832750c3d2c23441a5a587ca91d7a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305095"
---
# <a name="ipaddress-table"></a>IPAddress 表格
 
IPAddress 表會將 IP 位址對應至在經驗品質資料庫中其他地方使用的唯一 IP 位址識別碼。 此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |主要  <br/> |指定之 IP 位址的唯一識別碼。  <br/> |
|**IPAddress** <br/> |Varchar (50)   <br/> |Unique  <br/> |唯一的 IP 位址 (例如，189.168.1.1) 會對應至 IpAddressKey。 這可以是 IPv4 或 IPv6 位址。  <br/> |
   

