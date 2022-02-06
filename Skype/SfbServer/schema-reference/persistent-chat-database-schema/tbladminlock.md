---
title: tblAdminLock
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。
---

# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime，非 null  <br/> |鎖定到期的日期和時間。擁有者可定期延長這個值。  <br/> |
|lockServerID  <br/> |int，非 null  <br/> |掌握鎖定之伺服器的識別碼。  <br/> |
|lockActorID  <br/> |int，非 null  <br/> |掌握鎖定之主體的識別碼。  <br/> |
   

