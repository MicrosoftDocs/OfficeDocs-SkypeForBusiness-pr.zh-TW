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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192756"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime、not null  <br/> |[鎖定到期日] 和 [時間]。 擁有者可以定期延伸此值。  <br/> |
|lockServerID  <br/> |int, not null  <br/> |擁有鎖定的伺服器 ID。  <br/> |
|lockActorID  <br/> |int, not null  <br/> |擁有鎖定之主體的 ID。  <br/> |
   

