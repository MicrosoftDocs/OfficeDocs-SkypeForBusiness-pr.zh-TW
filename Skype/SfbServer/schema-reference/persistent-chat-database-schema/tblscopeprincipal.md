---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含指派給節點的作用中。
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812441"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal 包含指派給節點的作用中。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int，not null  <br/> |作用中所適用的節點識別碼。  <br/> |
|scopePrinID  <br/> |int，not null  <br/> |Principal ID。  <br/> |
|scopeIsDenied  <br/> |bit、not null  <br/> |如果範圍類型為 Deny，則為 True;如果允許，則為 False。  <br/> |
|scopeUpdatedBy  <br/> |int，not null  <br/> |上次更新此專案的主體 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |主鍵。  <br/> |
|scopeNodeID  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
|scopePrinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

