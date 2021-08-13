---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。
ms.openlocfilehash: 2b03473b6f89e0dd2f572e2462b607bc72a2a2eb5f83aa18d2d779f9f66ee220
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318676"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int，非 null  <br/> |角色類型識別碼。  <br/> |
|rtypeDesc  <br/> |nvarchar (256)，非 null  <br/> | 角色類型描述。以下是四個可用的角色： <br/>  Member：聊天室成員 <br/>  Manager：聊天室管理員 <br/>  Voiced：視聽中心聊天室簡報者 <br/>  Creator：可建立聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |bigint，非 null  <br/> | 角色的權限組。使用的位元如下： <br/>  2: 若角色可管理節點則為 True。 <br/>  4: 若角色可建立子節點則為 True。 <br/>  7: 若角色可加入聊天室 (或類別的子聊天室) 則為 True。 <br/>  8: 若角色可在聊天室 (或類別的子聊天室) 中交談則為 True。 <br/>  10: 若角色可讀取聊天記錄則為 True (即使未加入聊天室時亦可)。 <br/>  11: 若角色可看到聊天室則為 True (可進一步依據範圍和可見度等因素來調整)。 <br/>  12: 若角色可在視聽中心聊天室中交談則為 True。 <br/>  13: 若角色可在檢視節點時略過可見度規則則為 True。 <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|rtypeID  <br/> |主索引鍵。  <br/> |
   

