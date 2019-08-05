---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主體成員資格。
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192716"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主體成員資格。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|memberADPath  <br/> |Nvarchar (384), not null  <br/> |成員的判別名。 成員不一定要是 principal (在 tblPrincipal 資料表中)。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal 中使用 [查閱] 的外鍵。  <br/> |
   

