---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。
ms.openlocfilehash: ad3b2543e2715462b953c611c8b5f24ea7885a6cb910931aa5b832b8196856eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351942"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，非 null  <br/> |鎖定到期的日期和時間。擁有者可定期延長這個值。  <br/> |
|lockServerID  <br/> |int，非 null  <br/> |掌握鎖定之伺服器的識別碼。  <br/> |
|lockActorID  <br/> |int，非 null  <br/> |掌握鎖定之主體的識別碼。  <br/> |
   

