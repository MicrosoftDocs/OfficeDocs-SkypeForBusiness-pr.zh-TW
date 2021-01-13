---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831533"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|ptypeID  <br/> |smallint，非 null  <br/> |主體類型識別碼。  <br/> |
|ptypeDesc  <br/> |nvarchar (256)，非 null  <br/> |類型的描述。  <br/> |
|ptypeIsSystemUser  <br/> |bit，非 null  <br/> |如果類型對應至作為內部用途的主體，則為 True。  <br/> |
|ptypeIsUser  <br/> |bit，非 null  <br/> |如果類型為使用者類型，則為 True。  <br/> |
   
**Key**

|**欄**|**描述**|
|:-----|:-----|
|ptypeID  <br/> |主索引鍵。  <br/> |
   
**主體值**

|**識別碼**|**Role**|**描述**|**使用者**|
|:-----|:-----|:-----|:-----|
|1   <br/> |任何  <br/> |不含已知類型的一般主體。不使用在 tblPrincipal 表格中。  <br/> ||
|2   <br/> |AnyUser  <br/> |使用者類型的一般主體。不使用在 tblPrincipal 表格中。  <br/> |是  <br/> |
|3   <br/> |AnyGroup  <br/> |含群組語意的一般主體。不使用在 tblPrincipal 表格中。  <br/> ||
|4   <br/> |SystemUser  <br/> |Persistent Chat Server 內部使用的主體。  <br/> ||
|5   <br/> |使用者  <br/> |一般使用者。  <br/> |是  <br/> |
|8   <br/> |直流  <br/> |Active Directory 網域服務網域控制站。  <br/> ||
|9   <br/> |群組  <br/> |Active Directory 安全性群組。  <br/> ||
|10   <br/> |資料夾  <br/> |Active Directory 容器或組織單位。  <br/> ||
   
## <a name="see-also"></a>另請參閱

[tblPrincipal](tblprincipal.md)
