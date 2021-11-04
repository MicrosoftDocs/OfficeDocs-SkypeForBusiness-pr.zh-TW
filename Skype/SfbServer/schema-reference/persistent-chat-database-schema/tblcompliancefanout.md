---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含處理符合性事件的所有伺服器。
ms.openlocfilehash: 6c0ae5a9b00945494c125511e1206f4177432703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765071"
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
   

