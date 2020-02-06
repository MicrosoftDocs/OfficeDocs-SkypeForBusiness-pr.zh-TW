---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含已處理合規性事件的所有伺服器。
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814651"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含已處理合規性事件的所有伺服器。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |伺服器身分識別（對應至 tblServerIdentity serverID 表）。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|fanoutEventID  <br/> |在 tblComplianceData cmplEventID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

