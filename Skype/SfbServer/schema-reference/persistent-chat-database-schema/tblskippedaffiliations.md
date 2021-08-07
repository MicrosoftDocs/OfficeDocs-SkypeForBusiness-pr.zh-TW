---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含無法讀取的隸屬 (，通常是因為 Active Directory 網域服務存取錯誤) 。
ms.openlocfilehash: ddc8ef78f083235ccde122a3f26fd7f37e34b71d9643b1c729f802e3e080c413
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305365"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含無法讀取的隸屬 (，通常是因為 Active Directory 網域服務存取錯誤) 。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|affDescription  <br/> |nvarchar (255)，非 null  <br/> |識別關係的字串。  <br/> 格式為： guid：  _{0}_ uri： _{1}_> 識別碼：  _{2}_ <br/> |
|updatedBy  <br/> |int，非 null  <br/> |上次更新此列之主體的識別碼。其一律為 1 (系統使用者) 因為 Active Directory 同步處理是這些項目的唯一來源。  <br/> |
   
**Keys**

|**欄 (s)**|**描述**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主索引鍵。  <br/> |
|Tblprincipal.prinid  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
   

