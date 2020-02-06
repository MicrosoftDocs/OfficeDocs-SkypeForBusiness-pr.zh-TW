---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814471"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|principalID  <br/> |int，not null  <br/> |附屬原則的 ID。  <br/> |
|affiliationID  <br/> |int，not null  <br/> |代表隸屬關係的承擔者 ID。 每個主體（除系統使用者類型之外）都有自我隸屬關係。  <br/> |
|index  <br/> |int，not null  <br/> |Index. 自我隸屬關係的值是-1，而其他隸屬關係則會依序從每個\<PrincipalID、affiliationId\> bucket 中的1增加。  <br/> |
|updatedBy  <br/> |int，not null  <br/> |已進行最新更新的主體。 這通常是1，這表示 Active Directory 同步處理。  <br/> |
   
**鍵**

|**分欄**|**說明**|
|:-----|:-----|
|\<principalID、index、affiliationID\>  <br/> |主鍵。  <br/> |
|principalID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
|affiliationID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

