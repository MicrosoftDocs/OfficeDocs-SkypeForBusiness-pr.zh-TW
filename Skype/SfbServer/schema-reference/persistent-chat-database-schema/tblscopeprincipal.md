---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含指派給節點的範圍。
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831513"
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
   

