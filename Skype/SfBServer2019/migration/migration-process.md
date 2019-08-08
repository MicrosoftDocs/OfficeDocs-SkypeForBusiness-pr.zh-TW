---
title: 遷移程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 商務用 Skype Server 2019 的建議和支援的遷移程式是並排遷移。 本主題描述為什麼您應該使用並列移植, 同時還包含共存測試的相關資訊。
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238083"
---
# <a name="migration-process"></a><span data-ttu-id="209ff-104">遷移程式</span><span class="sxs-lookup"><span data-stu-id="209ff-104">Migration process</span></span>

<span data-ttu-id="209ff-105">商務用 Skype Server 2019 的建議和支援的遷移程式是並排遷移。</span><span class="sxs-lookup"><span data-stu-id="209ff-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="209ff-106">本主題描述為什麼您應該使用並列移植, 同時還包含共存測試的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="209ff-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="209ff-107">並行遷移</span><span class="sxs-lookup"><span data-stu-id="209ff-107">Side-By-Side Migration</span></span>

<span data-ttu-id="209ff-108">在幾乎所有的遷移中, 您都應該使用並行遷移路徑。</span><span class="sxs-lookup"><span data-stu-id="209ff-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="209ff-109">在並列式遷移中, 您可以使用商務用 Skype Server 2019 以及執行舊版的對應伺服器以及將作業轉移到新伺服器的方式, 來部署新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="209ff-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="209ff-110">如果需要回滾到前一個版本, 您只需要將操作移回原始伺服器。</span><span class="sxs-lookup"><span data-stu-id="209ff-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="209ff-111">請注意, 在這種情況下, 使用升級後的用戶端排程的新會議將無法運作, 而且用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="209ff-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="209ff-112">共存測試</span><span class="sxs-lookup"><span data-stu-id="209ff-112">Coexistence Testing</span></span>

<span data-ttu-id="209ff-113">將商務用 Skype Server 2019 與早期版本並行部署之後, 部署代表商務用 Skype Server 2019 與舊版的共存測試狀態。</span><span class="sxs-lookup"><span data-stu-id="209ff-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="209ff-114">當處於這個狀態時, 請務必測試並確定服務已啟動、可管理每個網站, 而且用戶端可以與目前與舊版使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="209ff-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="209ff-115">在遷移所有使用者之前, 請務必瞭解每個部署的狀態, 並確保每個部署都能正常運作且正常運作。</span><span class="sxs-lookup"><span data-stu-id="209ff-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="209ff-116">通常, 共存測試階段會在整個商務用 Skype Server 2019 的試驗測試中存在。</span><span class="sxs-lookup"><span data-stu-id="209ff-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="209ff-117">舊版使用者會在一段時間內移至商務用 Skype Server 2019, 以確保應用程式相容性及功能及功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="209ff-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="209ff-118">先導測試之後, 使用者和應用程式會移至商務用 Skype Server 2019 的生產版本, 而舊版池和舊版本的應用程式就會停用。</span><span class="sxs-lookup"><span data-stu-id="209ff-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
