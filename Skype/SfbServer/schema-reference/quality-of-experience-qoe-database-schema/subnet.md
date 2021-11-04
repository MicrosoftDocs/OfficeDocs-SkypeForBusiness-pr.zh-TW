---
title: Subnet 表格
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。
ms.openlocfilehash: b0c10fae89fe76c184e3aaffec4e1166c4cdb94c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768311"
---
# <a name="subnet-table"></a>Subnet 表格
 
Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主要、外部  <br/> |子網路 IP 的整數表示。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子網路遮罩。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |從 [UserSite 表格](usersite.md)中參照。  <br/> |
|**SubnetDescription** <br/> |Nvarchar (512)   <br/> ||子網路的描述。  <br/> |
   

