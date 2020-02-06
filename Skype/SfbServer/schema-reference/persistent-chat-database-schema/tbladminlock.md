---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814691"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime、not null  <br/> |[鎖定到期日] 和 [時間]。 擁有者可以定期延伸此值。  <br/> |
|lockServerID  <br/> |int，not null  <br/> |擁有鎖定的伺服器 ID。  <br/> |
|lockActorID  <br/> |int，not null  <br/> |擁有鎖定之主體的 ID。  <br/> |
   

