---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服務之間的目前對等連線。
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192760"
---
# <a name="tblactivepeers"></a><span data-ttu-id="57c27-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="57c27-103">tblActivePeers</span></span>
 
<span data-ttu-id="57c27-104">tblActivePeers 包含聊天服務之間的目前對等連線。</span><span class="sxs-lookup"><span data-stu-id="57c27-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="57c27-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="57c27-105">**Columns**</span></span>

|<span data-ttu-id="57c27-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="57c27-106">**Column**</span></span>|<span data-ttu-id="57c27-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="57c27-107">**Type**</span></span>|<span data-ttu-id="57c27-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="57c27-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57c27-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="57c27-109">aplServerID</span></span>  <br/> |<span data-ttu-id="57c27-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="57c27-110">int, not null</span></span>  <br/> |<span data-ttu-id="57c27-111">已張貼專案之伺服器的 ID。</span><span class="sxs-lookup"><span data-stu-id="57c27-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="57c27-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="57c27-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="57c27-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="57c27-113">int, not null</span></span>  <br/> |<span data-ttu-id="57c27-114">張貼伺服器所連接之對等的 ID。</span><span class="sxs-lookup"><span data-stu-id="57c27-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="57c27-115">**鍵**</span><span class="sxs-lookup"><span data-stu-id="57c27-115">**Keys**</span></span>

|<span data-ttu-id="57c27-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="57c27-116">**Column**</span></span>|<span data-ttu-id="57c27-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="57c27-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57c27-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="57c27-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="57c27-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="57c27-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="57c27-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="57c27-120">aplServerID</span></span>  <br/> |<span data-ttu-id="57c27-121">在 tblServerIdentity serverID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="57c27-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="57c27-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="57c27-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="57c27-123">在 tblServerIdentity serverID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="57c27-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

