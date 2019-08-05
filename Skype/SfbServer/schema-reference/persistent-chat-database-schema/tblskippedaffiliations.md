---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含無法讀取的隸屬關係 (通常是由於 Active Directory 網域服務存取錯誤)。
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192702"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations 包含無法讀取的隸屬關係 (通常是由於 Active Directory 網域服務存取錯誤)。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|affDescription  <br/> |Nvarchar (256), not null  <br/> |標識隸屬關係的字串。  <br/> 格式為: guid: _{0}_ uri: _{1}_> 識別碼:_{2}_ <br/> |
|updatedBy  <br/> |int, not null  <br/> |更新此列之主體的 ID。 因為 Active Directory 同步處理是這些專案的唯一來源, 所以它永遠是 1 (系統使用者)。  <br/> |
   
**鍵**

|**欄 (s)**|**說明**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

