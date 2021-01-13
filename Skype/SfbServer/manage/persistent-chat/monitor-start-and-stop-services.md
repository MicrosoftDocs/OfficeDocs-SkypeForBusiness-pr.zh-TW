---
title: 在商務用 Skype Server 2015 中監控、啟動和停止持續性聊天服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 摘要：瞭解如何在商務用 Skype Server 2015 中開始、停止和監視 Persistent 聊天服務。
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814133"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="c1f24-103">在商務用 Skype Server 2015 中監控、啟動和停止持續性聊天服務</span><span class="sxs-lookup"><span data-stu-id="c1f24-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c1f24-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中開始、停止和監視 Persistent 聊天服務。</span><span class="sxs-lookup"><span data-stu-id="c1f24-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c1f24-105">Persistent Chat service 和 Persistent Chat 服務規範服務是商務用 Skype 伺服器拓撲的一部分，因此可使用下列 Cmdlet 進行監控、停止和啟動：</span><span class="sxs-lookup"><span data-stu-id="c1f24-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c1f24-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="c1f24-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="c1f24-107">傳回以 Windows 服務執行之商務用 Skype Server 2015 元件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c1f24-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="c1f24-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="c1f24-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="c1f24-109">啟動服務。</span><span class="sxs-lookup"><span data-stu-id="c1f24-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="c1f24-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="c1f24-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="c1f24-111">停止服務。</span><span class="sxs-lookup"><span data-stu-id="c1f24-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c1f24-112">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="c1f24-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c1f24-113">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="c1f24-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="c1f24-114">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="c1f24-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c1f24-115">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="c1f24-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="c1f24-116">如需如何使用 Cmdlet 的詳細資訊，請參閱 [商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="c1f24-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

