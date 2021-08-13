---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。
ms.openlocfilehash: 5eb67681e5823b8549deb01b44e0bcb771e26882a2cd713d9cf598ae0670335b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341668"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|principalID  <br/> |int，非 null  <br/> |附屬主體的識別碼。  <br/> |
|affiliationID  <br/> |int，非 null  <br/> |代表隸屬關係之主體的識別碼。 除了系統使用者類型) 之外，每個主體 (都具有自我從屬。  <br/> |
|index  <br/> |int，非 null  <br/> |指數。 「自身隸屬于-1」的值是-1，另一個隸屬關係會依序從每個桶中的1增加 \<principalID, affiliationId\> 。  <br/> |
|updatedBy  <br/> |int，非 null  <br/> |進行最新更新的主體。 這通常是1，表示 Active Directory 同步處理。  <br/> |
   
**Keys**

|**Columns**|**描述**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |主索引鍵。  <br/> |
|principalID  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
|affiliationID  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
   

