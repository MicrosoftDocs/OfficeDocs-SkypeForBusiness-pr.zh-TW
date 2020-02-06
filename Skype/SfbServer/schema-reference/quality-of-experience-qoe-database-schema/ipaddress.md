---
title: '[IPAddress] 表格'
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: '[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809541"
---
# <a name="ipaddress-table"></a>[IPAddress] 表格
 
[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |首選  <br/> |指定 IP 位址的唯一識別碼。  <br/> |
|**IPAddress** <br/> |Varchar （50）  <br/> |唯一  <br/> |對應至 IpAddressKey 的唯一 IP 位址（例如，189.168.1.1）。 這可能是 IPv4 或 IPv6 位址。  <br/> |
   

