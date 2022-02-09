---
title: tblComplianceFanout
ms.reviewer: ''
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含處理符合性事件的所有伺服器。
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420876"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含處理符合性事件的所有伺服器。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件識別碼。  <br/> |
|fanoutServerID  <br/> |int  <br/> |與 tblServerIdentity.serverID table) 相對應的伺服器身分識別 (。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|fanoutEventID  <br/> |在 tblComplianceData.cmplEventID 表格中查閱的外鍵。  <br/> |
   

