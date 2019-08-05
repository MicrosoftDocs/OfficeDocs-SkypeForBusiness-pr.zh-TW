---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更 (新增和移除的成員)。
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192722"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更 (新增和移除的成員)。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, 不是 null  <br/> |已變更之群組的主要 GUID。  <br/> |
|memberADPath  <br/> |Nvarchar (256)  <br/> |成員的判別名。  <br/> |
|memberRemoved  <br/> |bit、not null  <br/> |如果成員已新增, 則為 False。 如果成員已移除, 則為 True。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主鍵。  <br/> |
   

