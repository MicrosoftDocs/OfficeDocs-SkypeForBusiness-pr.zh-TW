---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含處理符合性事件的所有伺服器。
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809793"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含處理符合性事件的所有伺服器。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件識別碼。  <br/> |
|fanoutServerID  <br/> |int  <br/> |與 tblServerIdentity.serverID table) 相對應的伺服器身分識別 (。  <br/> |
   
**Key**

|**欄**|**描述**|
|:-----|:-----|
|fanoutEventID  <br/> |在 tblComplianceData.cmplEventID 表格中查閱的外鍵。  <br/> |
   

