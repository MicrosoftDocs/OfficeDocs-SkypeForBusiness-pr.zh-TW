---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。
ms.openlocfilehash: 5fbd22de596de45664ce3340e9d85ee935ba07e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763271"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255)，非 null  <br/> |通道統一資源識別項 (URI)。  <br/> |
|userId  <br/> |int，非 null  <br/> |參與者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。  <br/> |
|joinedAt  <br/> |bigint，非 null  <br/> |加入活動的時間戳記。  <br/> |
|partedAt  <br/> |Bigint  <br/> |如果參與者仍加入，則為 Null。如果不是 Null，則是通道離開事件的時間戳記。  <br/> 當所有轉譯器處理事件時，這些項目最後都會移除。  <br/> |
|userUri  <br/> |nvarchar(255)，非 null  <br/> |使用者 URI。  <br/> |
|serverID  <br/> |int  <br/> |伺服器識別碼 (如 tblServerIdentity.serverID 表格中所示)。  <br/> |
|sessionId  <br/> |Bigint  <br/> |伺服器工作階段。這是聊天服務每次啟動時，所產生的隨機號碼。在識別孤立的參與者時，可使用此號碼來區別工作階段。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |主索引鍵。  <br/> |
   

