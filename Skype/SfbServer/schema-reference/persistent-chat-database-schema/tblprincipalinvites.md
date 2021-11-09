---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。
ms.openlocfilehash: d7993cba89474fe5d7343cd25f39c3363b8be866
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864580"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|尹雯德  <br/> |int，非 null  <br/> |從 tblLastInviteId 表格產生的唯一序號 (每個主體識別碼)。  <br/> |
|nodeID  <br/> |int，非 null  <br/> |節點識別碼 (僅限聊天室)。  <br/> |
|createdOn  <br/> |日期時間，非 null  <br/> |建立的時間。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |主索引鍵。  <br/> |
|Tblprincipal.prinid  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
|nodeID  <br/> |在 tblNode.nodeID 表格中查閱外部索引鍵。  <br/> |
   

