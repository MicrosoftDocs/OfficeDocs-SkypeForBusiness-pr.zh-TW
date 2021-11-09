---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: a4b17a234b8efe1b661c1ebbe31a8ed34b0d5935
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854097"
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
   

