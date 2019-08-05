---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192723"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|invID  <br/> |int, not null  <br/> |從 tblLastInviteId 資料表產生的唯一順序編號 (每個主體識別碼)。  <br/> |
|個  <br/> |int, not null  <br/> |節點識別碼 (僅適用于聊天室)。  <br/> |
|createdOn  <br/> |datetime、not null  <br/> |建立時間。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prinID、\>  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
|個  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
   

