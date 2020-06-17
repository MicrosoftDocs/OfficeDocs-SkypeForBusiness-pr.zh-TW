---
title: 移除舊版封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果舊版部署包含封存伺服器或監控伺服器，在遷移至商務用 Skype Server 2019 之後，只要所有使用者都已從其他的舊版集區中移除，這些伺服器就可以從舊版環境中移除。 您可以依任何順序移除封存伺服器或監控伺服器。 重要的一點是，所有的使用者都已經從其他的舊版集區中移除。
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752165"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="c27b7-105">移除舊版封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="c27b7-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="c27b7-106">如果舊版部署包含封存伺服器或監控伺服器，在遷移至商務用 Skype Server 2019 之後，就可以從舊版環境中移除這些伺服器，但前提是所有使用者都已從其餘的舊版集區中移除。</span><span class="sxs-lookup"><span data-stu-id="c27b7-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="c27b7-107">您可以依任何順序移除封存伺服器或監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="c27b7-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="c27b7-108">重要的一點是，所有的使用者都已經從其他的舊版集區中移除。</span><span class="sxs-lookup"><span data-stu-id="c27b7-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="c27b7-109">您可以遵循[階段4：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區中所述的程式，將使用者移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="c27b7-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="c27b7-110">確認所有使用者都已從任何剩餘的集區中移除之後，請 decommision 伺服器並移除角色。</span><span class="sxs-lookup"><span data-stu-id="c27b7-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="c27b7-111">不過，已過期，但相關的範例是「卸載 Microsoft Lync Server 並移除伺服器角色」，其可在這裡下載 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) 。</span><span class="sxs-lookup"><span data-stu-id="c27b7-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

