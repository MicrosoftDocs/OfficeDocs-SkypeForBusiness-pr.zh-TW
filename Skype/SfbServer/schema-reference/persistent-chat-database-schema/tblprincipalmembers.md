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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主體成員資格。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813941"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主體成員資格。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |Principal ID。  <br/> |
|memberADPath  <br/> |Nvarchar （384），not null  <br/> |成員的判別名。 成員不一定要是 principal （在 tblPrincipal 資料表中）。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal 中使用 [查閱] 的外鍵。  <br/> |
   

