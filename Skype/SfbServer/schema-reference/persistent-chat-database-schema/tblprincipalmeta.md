---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831543"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|prinAffiliationsDirty  <br/> |位元，非 null  <br/> |若主體關係必須重新整理，則為 True。  <br/> |
|prinAttributesDirty  <br/> |位元，非 null  <br/> |若主體屬性必須重新整理，則為 True。  <br/> |
|prinDeleted  <br/> |位元，非 null  <br/> |若主體已刪除，則為 True。  <br/> |
|tryCount  <br/> |int  <br/> |至今嘗試從 AD DS 重新整理主體的次數。  <br/> |
|lastTry  <br/> |datetime  <br/> |最近一次嘗試重新整理主體的時間戳記。若尚未重新整理過，可以是 null。  <br/> |
|nextTry  <br/> |datetime  <br/> |排定下次重新整理時間戳記。若未排定之後的重新整理，可以是 null。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|Tblprincipal.prinid  <br/> |主索引鍵。  <br/> |
|Tblprincipal.prinid  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
   

