---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812271"
---
# <a name="tblserveridentity"></a><span data-ttu-id="aca01-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="aca01-103">tblServerIdentity</span></span>
 
<span data-ttu-id="aca01-104">tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="aca01-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="aca01-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="aca01-105">**Columns**</span></span>

|<span data-ttu-id="aca01-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="aca01-106">**Column**</span></span>|<span data-ttu-id="aca01-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="aca01-107">**Type**</span></span>|<span data-ttu-id="aca01-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="aca01-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aca01-109">serverID</span><span class="sxs-lookup"><span data-stu-id="aca01-109">serverID</span></span>  <br/> |<span data-ttu-id="aca01-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="aca01-110">int, not null</span></span>  <br/> |<span data-ttu-id="aca01-111">[伺服器識別碼]。</span><span class="sxs-lookup"><span data-stu-id="aca01-111">Server ID.</span></span> <span data-ttu-id="aca01-112">與中央管理存放區中的實例識別碼相對應。</span><span class="sxs-lookup"><span data-stu-id="aca01-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="aca01-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="aca01-113">serverAddress</span></span>  <br/> |<span data-ttu-id="aca01-114">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="aca01-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="aca01-115">使用 Windows Communication Foundation 位址的伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="aca01-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="aca01-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="aca01-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="aca01-117">datetime</span><span class="sxs-lookup"><span data-stu-id="aca01-117">datetime</span></span>  <br/> |<span data-ttu-id="aca01-118">頻道伺服器更新此列以提供其所執行證據的最晚時間。</span><span class="sxs-lookup"><span data-stu-id="aca01-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="aca01-119">**機碼**</span><span class="sxs-lookup"><span data-stu-id="aca01-119">**Key**</span></span>

|<span data-ttu-id="aca01-120">**左欄**</span><span class="sxs-lookup"><span data-stu-id="aca01-120">**Column**</span></span>|<span data-ttu-id="aca01-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="aca01-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aca01-122">serverID</span><span class="sxs-lookup"><span data-stu-id="aca01-122">serverID</span></span>  <br/> |<span data-ttu-id="aca01-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="aca01-123">Primary key.</span></span>  <br/> |
   

