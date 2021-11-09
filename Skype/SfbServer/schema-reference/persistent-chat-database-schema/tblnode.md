---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode 包含類別或聊天室節點 (的物件樹) 如控制台和管理 Cmdlet 中所管理。
ms.openlocfilehash: 1e6d3a97f04d614a0993ca06d8a5b2a2f928b39d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846246"
---
# <a name="tblnode"></a>tblNode
 
tblNode 包含類別或聊天室節點 (的物件樹) 如控制台和管理 Cmdlet 中所管理。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|nodeID  <br/> |int，非 null  <br/> |節點識別碼 (唯一編號) 。  <br/> |
|nodeGuid  <br/> |GUID，非 null  <br/> |節點 GUID。  <br/> |
|parentID  <br/> |int  <br/> |父系的節點識別碼。 識別碼為 1) 的根節點 (也會將其本身包含為上層。  <br/> |
|nodeType  <br/> |位元，非 null  <br/> |True 是表示如果節點為類別。  <br/> False 表示節點為聊天室。  <br/> |
|nodeName  <br/> |nvarchar (256)，非 null  <br/> |節點名稱。  <br/> |
|nodeDesc  <br/> |nvarchar (256)，非 null  <br/> |節點描述。  <br/> |
|邀請  <br/> |位  <br/> | 類別： <br/>  True 是表示如果邀請已開啟。 <br/>  為 False，則邀請為關閉狀態。 <br/>  會議室： <br/>  False 如果邀請已關 (會覆寫父類別) 。 <br/>  如果 [邀請] 設定繼承自父系類別，則為 Null。 <br/> |
|登錄  <br/> |位  <br/> | 類別： <br/>  True 是表示如果聊天記錄開啟。 <br/>  為 False，則聊天記錄為關閉狀態。 <br/>  會議室： <br/>  空。 <br/> |
|filePost  <br/> |位  <br/> | 類別： <br/>  True 是表示如果允許檔案上傳。 <br/>  False 表示不允許檔案上傳。 <br/>  會議室： <br/>  空。 <br/> |
|禁用  <br/> |位元，非 null  <br/> |True 是表示如果停用聊天室。 僅適用于聊天室。  (類別為 False。 )   <br/> |
|行為  <br/> |smallint，非 null  <br/> | 在 EnumValue table) 中查閱 (行為： <br/>  4：正常 (一般聊天室) 。 <br/>  5：視聽中心 (視聽中心聊天室，只有簡報者可以參與) 。 <br/>  僅適用于聊天室。 <br/> |
|visibility  <br/> |smallint，非 null  <br/> | EnumValue table) 上查看的可見度 (： <br/>  2：私人 <br/>  3：範圍 <br/>  6：開啟 <br/>  僅適用于聊天室。 <br/> |
|siopID  <br/> |GUID  <br/> |Add-In GUID （如果增益集與此聊天室關聯）。  (類別沒有增益集。 )   <br/> 增益集資訊會在 SiopWhiteList 表格中進行查閱。  <br/> |
|nodeAddedBy  <br/> |int，非 null  <br/> |建立此節點之主體的識別碼。  <br/> |
|nodeAddedOn  <br/> |bigint，非 null  <br/> |建立節點的時間戳記。  <br/> |
|nodeUpdatedBy  <br/> |int，非 null  <br/> |進行此節點之最新更新之主體的識別碼。  <br/> |
|nodeUpdatedOn  <br/> |bigint，非 null  <br/> |此節點最新更新的時間戳記。  <br/> |
|purgedOn  <br/> |datetime  <br/> |最新的清除作業時間 (從影響此節點 tblPrincipalRole 表格) 移除 tblScopedPrincipal 資料表和角色中的範圍。 這是由聊天服務的內部快取更新機制使用。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|nodeID  <br/> |主索引鍵。  <br/> |
|行為  <br/> |在 tblEnumValue.valueID 表格中查閱的外鍵。  <br/> |
|visibility  <br/> |在 tblEnumValue.valueID 表格中查閱的外鍵。  <br/> |
|parentID  <br/> |在 tblNode.nodeID 表格中查閱外部索引鍵。  <br/> |
|siopID  <br/> |在 tblSiopWhiteList.siopId 表格中查閱的外鍵。  <br/> |
   

