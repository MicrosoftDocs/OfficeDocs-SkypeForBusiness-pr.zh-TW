---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812931"
---
# <a name="tblprincipaltype"></a>tblPrincipalType
 
tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|ptypeID  <br/> |Smallint，not null  <br/> |主體類型 ID。  <br/> |
|ptypeDesc  <br/> |Nvarchar （256），not null  <br/> |類型的描述。  <br/> |
|ptypeIsSystemUser  <br/> |bit、not null  <br/> |如果該類型對應到用於內部用途的主體，則為 True。  <br/> |
|ptypeIsUser  <br/> |bit、not null  <br/> |如果該類型是使用者類型，則為 True。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|ptypeID  <br/> |主鍵。  <br/> |
   
**主要值**

|**標識號**|**角色**|**說明**|**使用者**|
|:-----|:-----|:-----|:-----|
|1  <br/> |每  <br/> |沒有已知類型的一般原則。 在 tblPrincipal 表格中未使用。  <br/> ||
|2  <br/> |AnyUser  <br/> |使用者類型的一般主體。 在 tblPrincipal 表格中未使用。  <br/> |是  <br/> |
|3  <br/> |AnyGroup  <br/> |含有群組語義的一般主體。 在 tblPrincipal 表格中未使用。  <br/> ||
|4  <br/> |SystemUser  <br/> |永久聊天伺服器在內部使用的主要原則。  <br/> ||
|500  <br/> |使用者  <br/> |一般使用者。  <br/> |是  <br/> |
|型  <br/> |DC  <br/> |Active Directory 網域服務網網域控制站。  <br/> ||
|9  <br/> |群組  <br/> |Active Directory 安全性群組。  <br/> ||
|第  <br/> |資料夾  <br/> |Active Directory 容器或組織單位。  <br/> ||
   
## <a name="see-also"></a>另請參閱

[tblPrincipal](tblprincipal.md)
