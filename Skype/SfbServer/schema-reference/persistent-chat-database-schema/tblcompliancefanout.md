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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含已處理合規性事件的所有伺服器。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192748"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 包含已處理合規性事件的所有伺服器。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |事件 ID。  <br/> |
|fanoutServerID  <br/> |int  <br/> |伺服器身分識別 (對應至 tblServerIdentity serverID 表)。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|fanoutEventID  <br/> |在 tblComplianceData cmplEventID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

