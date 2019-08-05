---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 包含所有的承擔者, 包括使用者、資料夾和群組。
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192728"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 包含所有的承擔者, 包括使用者、資料夾和群組。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|prinGuid  <br/> |GUID, 不是 null  <br/> |主要 GUID。 這會被廣泛用做為備用主鍵, 因為它的意義是要與 Active Directory 網域服務空間相交。 (快取的主體的 GUID 等於對應的 Active Directory 物件 GUID。)  <br/> |
|prinUri  <br/> |Nvarchar (256), not null  <br/> |主體 URI。 SIP 配置適用于使用者, 而 ma grp 則用於幾乎所有其他專案。  <br/> |
|prinName  <br/> |Nvarchar (256)  <br/> |通用名稱。 僅供使用者類型使用。  <br/> |
|prinDisplayName  <br/> |NVarchar (256)  <br/> |顯示名稱。 僅供使用者類型使用。  <br/> |
|prinCompanyName  <br/> |Nvarchar (256)  <br/> |[公司名稱]。 僅供使用者類型使用。  <br/> |
|prinEmail  <br/> |Nvarchar (256)  <br/> |電子郵件。 僅供使用者類型使用。  <br/> |
|prinADPath  <br/> |Nvarchar (384)  <br/> |Principal 是其快取版本之 Active Directory 物件的功能變數名稱。 對於非 Active Directory 物件 (例如系統使用者) 的類型, 可以是 Null。  <br/> |
|prinADUserPrincipalName  <br/> |Nvarchar (256)  <br/> |使用者的使用者主體名稱 (UPN)。 只能由一般的使用者類型使用。  <br/> |
|prinDisabled  <br/> |Smallint, not null  <br/> | 0: 主體處於作用中狀態。 <br/>  1: 主體已停用, 因為使用者的 SIP 功能已停用。 <br/>  2: 由於相關聯的 AD 物件已遭刪除, 主體會被刪除。 <br/> |
|prinTypeID  <br/> |Smallint, not null  <br/> |主體類型 (從 tblPrincipalType 資料表)。  <br/> |
|prinPoolID  <br/> |Int  <br/> |主要使用者的商務用 Skype 用戶端池指派。  <br/> |
|prinPolicyID  <br/> |Int  <br/> |使用者的持續聊天伺服器原則值 (如果有標籤類型原則的話)。  <br/> |
|prinAddedBy  <br/> |int  <br/> |建立者的主體識別碼。  <br/> |
|prinAddedOn  <br/> |Bigint, not null  <br/> |建立時間的時間戳記。  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |上次更新此原則的主要使用者識別碼。  <br/> |
|prinUpdatedOn  <br/> |Bigint, not null  <br/> |上次更新的時間戳記。  <br/> |
|prinVerifiedOn  <br/> |datetime、not null  <br/> |主體上次 Active Directory 同步處理的日期和時間。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|prinID  <br/> |主鍵。  <br/> |
|prinTypeID  <br/> |在 tblPrincipalType ptypeID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

