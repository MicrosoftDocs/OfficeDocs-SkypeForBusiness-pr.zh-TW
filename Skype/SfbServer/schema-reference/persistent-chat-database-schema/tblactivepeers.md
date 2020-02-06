---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服務之間的目前對等連線。
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814711"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服務之間的目前對等連線。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，not null  <br/> |已張貼專案之伺服器的 ID。  <br/> |
|aplPeerID  <br/> |int，not null  <br/> |張貼伺服器所連接之對等的 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主鍵。  <br/> |
|aplServerID  <br/> |在 tblServerIdentity serverID 資料表中使用 [查閱] 的外鍵。  <br/> |
|aplPeerID  <br/> |在 tblServerIdentity serverID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

