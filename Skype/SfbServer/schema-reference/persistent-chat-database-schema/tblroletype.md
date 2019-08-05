---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一個靜態查閱表格, 其中包含角色類型及其關聯的許可權集。
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192710"
---
# <a name="tblroletype"></a>tblRoleType
 
tblRoleType 是一個靜態查閱表格, 其中包含角色類型及其關聯的許可權集。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|rtypeID  <br/> |int, not null  <br/> |角色類型 ID。  <br/> |
|rtypeDesc  <br/> |Nvarchar (256), not null  <br/> | 角色類型描述。 共有四個可用的角色: <br/>  成員: 聊天室成員 <br/>  管理員: 聊天室管理員 <br/>  濁音: auditorium 聊天室的簡報者 <br/>  建立者: 可以建立聊天室 <br/> |
|rtypeAllowedPermSet  <br/> |Bigint, not null  <br/> | 角色的許可權集。 已使用的位數如下: <br/>  2: 如果角色可以管理節點, 則為 True。 <br/>  4: 如果角色可以建立子節點, 則為 True。 <br/>  7: 如果角色可以加入聊天室 (或類別的子聊天室), 則為 True。 <br/>  8: 如果角色可以在聊天室 (或在子類別的 [兒童聊天室] 聊天室) 中聊天, 則為 True。 <br/>  10: True, 如果角色可以讀取聊天記錄, 即使未加入聊天室也一樣。 <br/>  11: 如果角色可以查看聊天室, 則為 True。 (例如範圍和可見度等因素進一步改進。) <br/>  12: 如果角色可以在 auditorium 聊天室中聊天, 則為 True。 <br/>  13: 如果角色在查看節點時可以略過可見度規則, 則為 True。 <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|rtypeID  <br/> |主鍵。  <br/> |
   

