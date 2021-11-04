---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。
ms.openlocfilehash: c5e8a4464b025b2e1d1b5775ca139b76a95ce633
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756182"
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
   

