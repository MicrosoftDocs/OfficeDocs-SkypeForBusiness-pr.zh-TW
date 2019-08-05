---
title: 監控、啟動和停止常設聊天室服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中啟動、停止及監視持續聊天服務。'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194064"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="871d7-103">監控、啟動和停止常設聊天室服務</span><span class="sxs-lookup"><span data-stu-id="871d7-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="871d7-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中啟動、停止及監視持續聊天服務。</span><span class="sxs-lookup"><span data-stu-id="871d7-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="871d7-105">持續式聊天服務和持續性聊天規範服務是商務用 Skype Server 拓撲的一部分, 因此可使用下列 Cmdlet 加以監視、停止及啟動:</span><span class="sxs-lookup"><span data-stu-id="871d7-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="871d7-106">CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="871d7-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="871d7-107">傳回作為 Windows 服務執行之商務用 Skype Server 2015 元件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="871d7-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="871d7-108">開始-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="871d7-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="871d7-109">啟動服務。</span><span class="sxs-lookup"><span data-stu-id="871d7-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="871d7-110">停止 CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="871d7-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="871d7-111">停止服務。</span><span class="sxs-lookup"><span data-stu-id="871d7-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="871d7-112">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="871d7-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="871d7-113">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="871d7-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="871d7-114">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="871d7-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="871d7-115">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="871d7-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="871d7-116">如需如何使用 Cmdlet 的詳細資訊, 請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="871d7-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

