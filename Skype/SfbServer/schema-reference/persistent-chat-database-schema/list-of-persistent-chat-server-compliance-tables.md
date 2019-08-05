---
title: 商務用 Skype Server 中的持續聊天伺服器合規性表格清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持續性聊天規範資料庫架構是由下清單格所組成。
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192770"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>商務用 Skype Server 中的持續聊天伺服器合規性表格清單
 
持續性聊天規範資料庫架構是由下清單格所組成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持續聊天伺服器合規性資料表清單

|**表格**|**說明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含已設定的配接器尚未處理的合規性事件。  <br/> 此表格包含持續與聊天相關的事件, 例如聊天訊息和檔案下載。 (TblComplianceParticipant 資料表會追蹤參與者事件)。  <br/> (在此資料表中處理事件的伺服器會列于 [tblComplianceFanout] 資料表中)。  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含已處理合規性事件的伺服器。 此表格與 tblComplianceData 資料表緊密結合。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每個聊天服務和每個伺服器的目前參與者。 它會根據從持久性聊天服務接收到的聯結和元件相容性事件來維護。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含全池相容性狀態資訊。  <br/> |
   

