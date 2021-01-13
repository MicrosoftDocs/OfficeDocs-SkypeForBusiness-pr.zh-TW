---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers 包含聊天服務之間目前的對等連線。
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812933"
---
# <a name="tblactivepeers"></a><span data-ttu-id="1ba20-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="1ba20-103">tblActivePeers</span></span>
 
<span data-ttu-id="1ba20-104">tblActivePeers 包含聊天服務之間目前的對等連線。</span><span class="sxs-lookup"><span data-stu-id="1ba20-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="1ba20-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="1ba20-105">**Columns**</span></span>

|<span data-ttu-id="1ba20-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="1ba20-106">**Column**</span></span>|<span data-ttu-id="1ba20-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="1ba20-107">**Type**</span></span>|<span data-ttu-id="1ba20-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="1ba20-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ba20-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="1ba20-109">aplServerID</span></span>  <br/> |<span data-ttu-id="1ba20-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="1ba20-110">int, not null</span></span>  <br/> |<span data-ttu-id="1ba20-111">張貼專案之伺服器的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1ba20-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="1ba20-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="1ba20-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="1ba20-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="1ba20-113">int, not null</span></span>  <br/> |<span data-ttu-id="1ba20-114">過帳伺服器連線的對等識別碼。</span><span class="sxs-lookup"><span data-stu-id="1ba20-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="1ba20-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="1ba20-115">**Keys**</span></span>

|<span data-ttu-id="1ba20-116">**欄**</span><span class="sxs-lookup"><span data-stu-id="1ba20-116">**Column**</span></span>|<span data-ttu-id="1ba20-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="1ba20-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="1ba20-118">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="1ba20-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1ba20-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="1ba20-119">aplServerID</span></span>  <br/> |<span data-ttu-id="1ba20-120">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1ba20-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="1ba20-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="1ba20-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="1ba20-122">在 tblServerIdentity.serverID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1ba20-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

