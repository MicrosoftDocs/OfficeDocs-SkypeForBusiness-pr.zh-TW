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
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="9d49b-103">商務用 Skype Server 中的 Persistent Chat Server 相容性資料表清單</span><span class="sxs-lookup"><span data-stu-id="9d49b-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="9d49b-104">Persistent Chat 規範資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="9d49b-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="9d49b-105">Persistent Chat Server 相容性表格清單</span><span class="sxs-lookup"><span data-stu-id="9d49b-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="9d49b-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="9d49b-106">**Table**</span></span>|<span data-ttu-id="9d49b-107">**描述**</span><span class="sxs-lookup"><span data-stu-id="9d49b-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9d49b-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="9d49b-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="9d49b-109">包含已設定之介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="9d49b-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="9d49b-110">此表格包含持續聊天相關的事件，例如聊天訊息和檔案下載。</span><span class="sxs-lookup"><span data-stu-id="9d49b-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="9d49b-111"> (參與者事件會由 tblComplianceParticipant 表追蹤。 ) </span><span class="sxs-lookup"><span data-stu-id="9d49b-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="9d49b-112"> (處理此表中之事件的伺服器會列在 tblComplianceFanout 表格中。 ) </span><span class="sxs-lookup"><span data-stu-id="9d49b-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="9d49b-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="9d49b-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="9d49b-114">包含處理規範事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9d49b-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="9d49b-115">此表格與 tblComplianceData 表格緊密結合。</span><span class="sxs-lookup"><span data-stu-id="9d49b-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="9d49b-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="9d49b-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="9d49b-117">包含每個聊天服務和每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="9d49b-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="9d49b-118">它會根據從 Persistent Chat service 接收的 join 和 part 相容性事件來維護。</span><span class="sxs-lookup"><span data-stu-id="9d49b-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="9d49b-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="9d49b-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="9d49b-120">包含集區範圍的相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="9d49b-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

