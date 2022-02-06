---
title: tblActivePeers
ms.reviewer: null
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服務之間目前的對等連線。
---

# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers 包含聊天服務之間目前的對等連線。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int，非 null  <br/> |張貼專案之伺服器的識別碼。  <br/> |
|aplPeerID  <br/> |int，非 null  <br/> |過帳伺服器連線的對等識別碼。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |主索引鍵。  <br/> |
|aplServerID  <br/> |在 tblServerIdentity.serverID 表格中查閱的外鍵。  <br/> |
|aplPeerID  <br/> |在 tblServerIdentity.serverID 表格中查閱的外鍵。  <br/> |
   

