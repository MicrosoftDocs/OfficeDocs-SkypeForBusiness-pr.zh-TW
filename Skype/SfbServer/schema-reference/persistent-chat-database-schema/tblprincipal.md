---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有主體，包括使用者、資料夾及群組。
ms.openlocfilehash: 9a2a48d0cd2dcb6b6ef078fd32625fc022f79c9f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635857"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有主體，包括使用者、資料夾及群組。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|prinGuid  <br/> |GUID，非 null  <br/> |主體 GUID。 因為它的意義會跨越 Active Directory 網域服務空間，所以這會被廣泛當作替代主鍵使用。  (快取主體的 GUID 等於對應的 Active Directory 物件 GUID。 )   <br/> |
|prinUri  <br/> |nvarchar (256)，非 null  <br/> |主體 URI。SIP 配置可用於使用者，而 ma-grp 幾乎可用於其他所有項目。  <br/> |
|prinName  <br/> |nvarchar(256)  <br/> |一般名稱。僅可用於使用者類型。  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |顯示名稱。僅可用於使用者類型。  <br/> |
|prinCompanyName  <br/> |nvarchar(256)  <br/> |公司名稱。僅可用於使用者類型。  <br/> |
|prinEmail  <br/> |nvarchar(256)  <br/> |電子郵件。僅可用於使用者類型。  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Active Directory 物件 (主體為快取版本) 的網域名稱。非 Active Directory 物件的類型可以是 Null (例如系統使用者)。  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar(256)  <br/> |使用者的使用者主要名稱 (UPN) 。 僅可用於一般使用者類型。  <br/> |
|prinDisabled  <br/> |smallint，非 null  <br/> | 0：主體為作用中狀態。 <br/>  1：主體已停用，因為使用者的 SIP 功能已停用。 <br/>  2：主體已刪除，因為相關聯的 AD 物件已刪除。 <br/> |
|prinTypeID  <br/> |smallint，非 null  <br/> |主體類型 (參照 tblPrincipalType 表格)。  <br/> |
|prinPoolID  <br/> |臨界值  <br/> |商務用 Skype 主體的用戶端集區指派。  <br/> |
|prinPolicyID  <br/> |臨界值  <br/> |如果存在標記類型原則，則為 user 的 Persistent Chat Server policy value。  <br/> |
|prinAddedBy  <br/> |int  <br/> |建立者的主體識別碼。  <br/> |
|prinAddedOn  <br/> |bigint，非 null  <br/> |建立時間的時間戳記。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |最近一次進行更新之主體的識別碼。  <br/> |
|prinUpdatedOn  <br/> |bigint，非 null  <br/> |最近一次更新的時間戳記。  <br/> |
|prinVerifiedOn  <br/> |datetime，非 null  <br/> |最近一次主體之 Active Directory Sync 重新整理的日期與時間。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|Tblprincipal.prinid  <br/> |主索引鍵。  <br/> |
|prinTypeID  <br/> |在 tblPrincipalType.ptypeID 表格中查閱外部索引鍵。  <br/> |
   

