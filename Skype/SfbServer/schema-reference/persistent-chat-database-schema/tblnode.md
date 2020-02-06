---
title: tblNode
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含物件樹狀結構（在 [類別] 或 [聊天室節點] 中），在 [控制台] 和 [管理 Cmdlet] 中是受管理的。
ms.openlocfilehash: 99300b6e26a0c173a13e6187680fd150ffa90e0a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814561"
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含物件樹狀結構（在 [類別] 或 [聊天室節點] 中），在 [控制台] 和 [管理 Cmdlet] 中是受管理的。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|個  <br/> |int，not null  <br/> |節點識別碼（唯一編號）。  <br/> |
|nodeGuid  <br/> |GUID，不是 null  <br/> |節點 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父級的節點識別碼。 根節點（含 ID 1）也會將它本身包含在父級中。  <br/> |
|nodeType  <br/> |bit、not null  <br/> |如果節點是類別，則為 True。  <br/> 如果該節點是聊天室，則為 False。  <br/> |
|nodeName  <br/> |Nvarchar （256），not null  <br/> |節點名稱。  <br/> |
|nodeDesc  <br/> |Nvarchar （256），not null  <br/> |[節點描述]。  <br/> |
|參加  <br/> |稍微  <br/> | 針對類別： <br/>  如果邀請開啟，則為 True。 <br/>  如果邀請關閉，則為 False。 <br/>  會議室： <br/>  如果邀請關閉，則為 False （覆寫上層類別）。 <br/>  如果 [邀請] 設定繼承自上層類別，則為 Null。 <br/> |
|註冊  <br/> |稍微  <br/> | 針對類別： <br/>  如果聊天記錄開啟，則為 True。 <br/>  如果聊天記錄為關閉，則為 False。 <br/>  會議室： <br/>  非. <br/> |
|filePost  <br/> |稍微  <br/> | 針對類別： <br/>  如果允許檔案上傳，則為 True。 <br/>  如果不允許檔案上傳，則為 False。 <br/>  會議室： <br/>  非. <br/> |
|禁止  <br/> |bit、not null  <br/> |如果停用聊天室，則為 True。 僅適用于聊天室。 （[類別] 為 False）。  <br/> |
|行為  <br/> |Smallint，not null  <br/> | 行為（在 EnumValue 資料表中查閱）： <br/>  4：標準（標準聊天室）。 <br/>  5： Auditorium （Auditorium 聊天室，只有簡報者可以參與）。 <br/>  僅適用于聊天室。 <br/> |
|看見  <br/> |Smallint，not null  <br/> | 可見度（在 EnumValue 表格上查閱）： <br/>  2：私人 <br/>  3：範圍 <br/>  6：開啟 <br/>  僅適用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |增益集 GUID （如果增益集與此聊天室相關聯）。 （類別沒有增益集）。  <br/> 增益集資訊是在 SiopWhiteList 表格中尋找。  <br/> |
|nodeAddedBy  <br/> |int，not null  <br/> |建立此節點之主體的 ID。  <br/> |
|nodeAddedOn  <br/> |Bigint，not null  <br/> |節點建立的時間戳記。  <br/> |
|nodeUpdatedBy  <br/> |int，not null  <br/> |已執行此節點最新更新之主體的 ID。  <br/> |
|nodeUpdatedOn  <br/> |Bigint，not null  <br/> |此節點最新更新的時間戳記。  <br/> |
|purgedOn  <br/> |datetime  <br/> |最新清除作業的時間（從 tblScopedPrincipal 資料表中移除作用中的範圍，以及從 tblPrincipalRole 資料表移除角色），這會影響這個節點。 這是由聊天服務的內部快取機制所使用。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|個  <br/> |主鍵。  <br/> |
|行為  <br/> |在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。  <br/> |
|看見  <br/> |在 tblEnumValue valueID 資料表中使用 [查閱] 的外鍵。  <br/> |
|parentID  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
|siopID  <br/> |在 tblSiopWhiteList siopId 資料表中使用 [查閱] 的外鍵。  <br/> |
   

