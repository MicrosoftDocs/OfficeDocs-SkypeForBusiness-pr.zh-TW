---
title: 商務用 Skype Server 中的 Persistent Chat Server 相容性資料表清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: Persistent Chat 規範資料庫架構是由下清單格所組成。
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813053"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>商務用 Skype Server 中的 Persistent Chat Server 相容性資料表清單
 
Persistent Chat 規範資料庫架構是由下清單格所組成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>Persistent Chat Server 相容性表格清單

|**Table**|**描述**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含已設定之介面卡尚未處理的規範事件。  <br/> 此表格包含持續聊天相關的事件，例如聊天訊息和檔案下載。  (參與者事件會由 tblComplianceParticipant 表追蹤。 )   <br/>  (處理此表中之事件的伺服器會列在 tblComplianceFanout 表格中。 )   <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含處理規範事件的伺服器。 此表格與 tblComplianceData 表格緊密結合。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每個聊天服務和每個伺服器的目前參與者。 它會根據從 Persistent Chat service 接收的 join 和 part 相容性事件來維護。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含集區範圍的相容性狀態資訊。  <br/> |
   

