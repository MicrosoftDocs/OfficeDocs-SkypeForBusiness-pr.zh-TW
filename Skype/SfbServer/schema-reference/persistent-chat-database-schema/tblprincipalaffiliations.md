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
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係, 包括 Active directory 網域服務安全性群組 (在 Active Directory 容器中, 在網域中)。
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192724"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係, 包括 Active directory 網域服務安全性群組 (在 Active Directory 容器中, 在網域中)。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|principalID  <br/> |int, not null  <br/> |附屬原則的 ID。  <br/> |
|affiliationID  <br/> |int, not null  <br/> |代表隸屬關係的承擔者 ID。 每個主體 (除系統使用者類型之外) 都有自我隸屬關係。  <br/> |
|index  <br/> |int, not null  <br/> |Index. 自我隸屬關係的值是-1, 而其他隸屬關係則會依序從每個\<PrincipalID、affiliationId\> bucket 中的1增加。  <br/> |
|updatedBy  <br/> |int, not null  <br/> |已進行最新更新的主體。 這通常是 1, 這表示 Active Directory 同步處理。  <br/> |
   
**鍵**

|**分欄**|**說明**|
|:-----|:-----|
|\<principalID、index、affiliationID\>  <br/> |主鍵。  <br/> |
|principalID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
|affiliationID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

