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
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="66c02-103">商務用 Skype Server 中的持續聊天伺服器合規性表格清單</span><span class="sxs-lookup"><span data-stu-id="66c02-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="66c02-104">持續性聊天規範資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="66c02-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="66c02-105">持續聊天伺服器合規性資料表清單</span><span class="sxs-lookup"><span data-stu-id="66c02-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="66c02-106">**表格**</span><span class="sxs-lookup"><span data-stu-id="66c02-106">**Table**</span></span>|<span data-ttu-id="66c02-107">**說明**</span><span class="sxs-lookup"><span data-stu-id="66c02-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="66c02-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="66c02-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="66c02-109">包含已設定的配接器尚未處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="66c02-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="66c02-110">此表格包含持續與聊天相關的事件, 例如聊天訊息和檔案下載。</span><span class="sxs-lookup"><span data-stu-id="66c02-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="66c02-111">(TblComplianceParticipant 資料表會追蹤參與者事件)。</span><span class="sxs-lookup"><span data-stu-id="66c02-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="66c02-112">(在此資料表中處理事件的伺服器會列于 [tblComplianceFanout] 資料表中)。</span><span class="sxs-lookup"><span data-stu-id="66c02-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="66c02-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="66c02-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="66c02-114">包含已處理合規性事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="66c02-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="66c02-115">此表格與 tblComplianceData 資料表緊密結合。</span><span class="sxs-lookup"><span data-stu-id="66c02-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="66c02-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="66c02-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="66c02-117">包含每個聊天服務和每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="66c02-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="66c02-118">它會根據從持久性聊天服務接收到的聯結和元件相容性事件來維護。</span><span class="sxs-lookup"><span data-stu-id="66c02-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="66c02-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="66c02-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="66c02-120">包含全池相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="66c02-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

