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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持續性聊天規範資料庫架構是由下清單格所組成。
ms.openlocfilehash: a992f00718d831af1b5a30f08baaf779ea3ee2c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814761"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a>商務用 Skype Server 中的持續聊天伺服器合規性表格清單
 
持續性聊天規範資料庫架構是由下清單格所組成。
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a>持續聊天伺服器合規性資料表清單

|**表格**|**說明**|
|:-----|:-----|
|[tblComplianceData](tblcompliancedata.md) <br/> |包含已設定的配接器尚未處理的合規性事件。  <br/> 此表格包含持續與聊天相關的事件，例如聊天訊息和檔案下載。 （TblComplianceParticipant 資料表會追蹤參與者事件）。  <br/> （在此資料表中處理事件的伺服器會列于 [tblComplianceFanout] 資料表中）。  <br/> |
|[tblComplianceFanout](tblcompliancefanout.md) <br/> |包含已處理合規性事件的伺服器。 此表格與 tblComplianceData 資料表緊密結合。  <br/> |
|[tblComplianceParticipant](tblcomplianceparticipant.md) <br/> |包含每個聊天服務和每個伺服器的目前參與者。 它會根據從持久性聊天服務接收到的聯結和元件相容性事件來維護。  <br/> |
|[tblComplianceState](tblcompliancestate.md) <br/> |包含全池相容性狀態資訊。  <br/> |
   

