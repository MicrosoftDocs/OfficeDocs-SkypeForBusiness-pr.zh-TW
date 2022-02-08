---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含指派給節點的範圍。
ms.openlocfilehash: 5805356a882b659c864bf8b071198bfe695f342d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394795"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含指派給節點的範圍。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int，非 null  <br/> |套用範圍的節點識別碼。  <br/> |
|scopePrinID  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|scopeIsDenied  <br/> |位元，非 null  <br/> |True 是表示如果範圍的類型是 Deny;False 表示允許。  <br/> |
|scopeUpdatedBy  <br/> |int，非 null  <br/> |最後更新此專案的主體識別碼。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |主索引鍵。  <br/> |
|scopeNodeID  <br/> |在 tblNode.nodeID 表格中查閱外部索引鍵。  <br/> |
|scopePrinID  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
   

