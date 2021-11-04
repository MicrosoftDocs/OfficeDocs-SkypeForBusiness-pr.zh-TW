---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主體成員資格。
ms.openlocfilehash: f1763244620d8ffd0ed86837b18eabc97bc72781
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749732"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers 包含主體成員資格。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|memberADPath  <br/> |Nvarchar (384) ，非 null  <br/> |成員的辨識名稱。 成員不一定要是 tblPrincipal table) 中的主體 (。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主索引鍵。  <br/> |
|Tblprincipal.prinid  <br/> |在 tblPrincipal.prinID 中查閱的外鍵。  <br/> |
   

