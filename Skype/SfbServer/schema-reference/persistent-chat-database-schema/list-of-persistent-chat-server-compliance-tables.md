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
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="6fb85-103">商務用 Skype Server 中的持續聊天伺服器合規性表格清單</span><span class="sxs-lookup"><span data-stu-id="6fb85-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="6fb85-104">持續性聊天規範資料庫架構是由下清單格所組成。</span><span class="sxs-lookup"><span data-stu-id="6fb85-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="6fb85-105">持續聊天伺服器合規性資料表清單</span><span class="sxs-lookup"><span data-stu-id="6fb85-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="6fb85-106">**表格**</span><span class="sxs-lookup"><span data-stu-id="6fb85-106">**Table**</span></span>|<span data-ttu-id="6fb85-107">**說明**</span><span class="sxs-lookup"><span data-stu-id="6fb85-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6fb85-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="6fb85-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="6fb85-109">包含已設定的配接器尚未處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="6fb85-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="6fb85-110">此表格包含持續與聊天相關的事件，例如聊天訊息和檔案下載。</span><span class="sxs-lookup"><span data-stu-id="6fb85-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="6fb85-111">（TblComplianceParticipant 資料表會追蹤參與者事件）。</span><span class="sxs-lookup"><span data-stu-id="6fb85-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="6fb85-112">（在此資料表中處理事件的伺服器會列于 [tblComplianceFanout] 資料表中）。</span><span class="sxs-lookup"><span data-stu-id="6fb85-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="6fb85-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="6fb85-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="6fb85-114">包含已處理合規性事件的伺服器。</span><span class="sxs-lookup"><span data-stu-id="6fb85-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="6fb85-115">此表格與 tblComplianceData 資料表緊密結合。</span><span class="sxs-lookup"><span data-stu-id="6fb85-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="6fb85-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="6fb85-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="6fb85-117">包含每個聊天服務和每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="6fb85-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="6fb85-118">它會根據從持久性聊天服務接收到的聯結和元件相容性事件來維護。</span><span class="sxs-lookup"><span data-stu-id="6fb85-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="6fb85-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="6fb85-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="6fb85-120">包含全池相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="6fb85-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

