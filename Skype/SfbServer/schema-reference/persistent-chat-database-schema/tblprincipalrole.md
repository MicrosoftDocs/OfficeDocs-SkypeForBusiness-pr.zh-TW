---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含指派給節點的明確角色。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192715"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole 包含指派給節點的明確角色。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |角色所套用的節點識別碼。  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |角色類型識別碼 (從 tblRoleType)。  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |上次更新此專案的主體 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主鍵。  <br/> |
|prinRoleNodeID  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
|prinRolePrinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
|prinRoleTypeID  <br/> |在 tblRoleType rtypeID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

