---
title: Subnet 表格
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。
ms.openlocfilehash: 92e582332e0e7c20c443a57c4ba0cc6abbb66cad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394595"
---
# <a name="subnet-table"></a>Subnet 表格
 
Subnet 表格是一種支援資料表。每筆記錄代表在網路組態設定中定義的一個子網路。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |主要、外部  <br/> |子網路 IP 的整數表示。  <br/> |
|**SubnetMask** <br/> |int  <br/> ||子網路遮罩。  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |從 [UserSite 表格](usersite.md)中參照。  <br/> |
|**SubnetDescription** <br/> |Nvarchar (512)   <br/> ||子網路的描述。  <br/> |
   

