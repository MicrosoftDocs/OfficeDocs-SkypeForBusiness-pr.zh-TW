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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: 子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192628"
---
# <a name="subnet-table"></a>Subnet 表格
 
子網資料表是支援表格。 每個記錄代表 [網路設定] 中定義的一個子網。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主要、外部  <br/> |子網 IP 的整數表示。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子網路遮罩。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |外  <br/> |從[UserSite 資料表](usersite.md)中參照。  <br/> |
|**SubnetDescription** <br/> |Nvarchar (512)  <br/> ||子網的描述。  <br/> |
   

