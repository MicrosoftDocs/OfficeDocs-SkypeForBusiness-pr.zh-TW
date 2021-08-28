---
title: tblPrincipalRole
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
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含指派給節點的明確角色。
ms.openlocfilehash: e899bc7763966ab3d7dd537aa162d8a716f958b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603792"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含指派給節點的明確角色。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int，非 null  <br/> |套用角色的節點識別碼。  <br/> |
|prinRolePrinID  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|prinRoleTypeID  <br/> |int，非 null  <br/> |TblRoleType) 的角色類型識別碼 (。  <br/> |
|prinRoleUpdatedBy  <br/> |int，非 null  <br/> |最後更新此專案的主體識別碼。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主索引鍵。  <br/> |
|prinRoleNodeID  <br/> |在 tblNode.nodeID 表格中查閱外部索引鍵。  <br/> |
|prinRolePrinID  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
|prinRoleTypeID  <br/> |在 tblRoleType.rtypeID 表格中查閱的外鍵。  <br/> |
   

