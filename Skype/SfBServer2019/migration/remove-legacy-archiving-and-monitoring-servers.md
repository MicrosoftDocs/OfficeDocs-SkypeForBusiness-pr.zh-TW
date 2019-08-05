---
title: 移除舊版的存檔與監視伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果您的舊版部署包含封存伺服器或監視伺服器, 在遷移到商務用 Skype Server 2019 之後, 只要所有使用者都已從任何其餘的舊版池中移除, 就可以從舊版環境中移除這些伺服器。 您可以以任何順序移除封存伺服器或監視伺服器。 主要需求是所有使用者都已從任何其餘的舊版池中移除。
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193281"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="b561a-105">移除舊版的存檔與監視伺服器</span><span class="sxs-lookup"><span data-stu-id="b561a-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="b561a-106">如果您的舊版部署包含封存伺服器或監視伺服器, 在遷移到商務用 Skype Server 2019 之後, 只要所有使用者都已從其餘的舊版池中移除, 就可以從舊版環境中移除這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="b561a-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="b561a-107">您可以以任何順序移除封存伺服器或監視伺服器。</span><span class="sxs-lookup"><span data-stu-id="b561a-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="b561a-108">主要需求是所有使用者都已從任何其餘的舊版池中移除。</span><span class="sxs-lookup"><span data-stu-id="b561a-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="b561a-109">您可以按照階段4所述的程式, 將使用者移至商務用 Skype Server 2019 [: 將測試使用者移至試驗](phase-4-move-test-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="b561a-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="b561a-110">確認所有使用者都已從任何剩餘的池中移除之後, 請 decommision 該伺服器並移除角色。</span><span class="sxs-lookup"><span data-stu-id="b561a-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="b561a-111">[已過期, 但相關] 範例是「卸載 Microsoft Lync Server 並移除伺服器角色」 (可在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)此下載)。</span><span class="sxs-lookup"><span data-stu-id="b561a-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

