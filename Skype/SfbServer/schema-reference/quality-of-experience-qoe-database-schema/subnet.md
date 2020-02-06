---
title: Subnet 表格
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805201"
---
# <a name="subnet-table"></a>Subnet 表格
 
子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主要、外部  <br/> |子網 IP 的整數表示。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子網路遮罩。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外  <br/> |從[UserSite 資料表](usersite.md)中參照。  <br/> |
|**SubnetDescription** <br/> |Nvarchar （512）  <br/> ||子網的描述。  <br/> |
   

