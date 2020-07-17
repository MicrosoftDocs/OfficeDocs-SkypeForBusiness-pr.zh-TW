---
title: 移轉程序
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
description: 商務用 Skype Server 2019 的建議和支援的遷移程式是並列式遷移。 本主題說明應使用並存移轉的原因，並包含共存測試的相關資訊。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752635"
---
# <a name="migration-process"></a><span data-ttu-id="63817-104">移轉程序</span><span class="sxs-lookup"><span data-stu-id="63817-104">Migration process</span></span>

<span data-ttu-id="63817-105">商務用 Skype Server 2019 的建議和支援的遷移程式是並列式遷移。</span><span class="sxs-lookup"><span data-stu-id="63817-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="63817-106">本主題說明應使用並存移轉的原因，並包含共存測試的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="63817-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="63817-107">並存移轉</span><span class="sxs-lookup"><span data-stu-id="63817-107">Side-By-Side Migration</span></span>

<span data-ttu-id="63817-108">幾乎在每種移轉時，您都應該使用並存移轉路徑。</span><span class="sxs-lookup"><span data-stu-id="63817-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="63817-109">在並列式遷移中，您可以使用商務用 Skype Server 2019 和執行舊版的相對應伺服器來部署新的伺服器，然後將作業轉移至新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="63817-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="63817-110">若要回復先前的版本，您只需要將作業移回原始伺服器。</span><span class="sxs-lookup"><span data-stu-id="63817-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="63817-111">請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。</span><span class="sxs-lookup"><span data-stu-id="63817-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="63817-112">共存測試</span><span class="sxs-lookup"><span data-stu-id="63817-112">Coexistence Testing</span></span>

<span data-ttu-id="63817-113">在與舊版一起部署商務用 Skype Server 2019 後，部署代表商務用 Skype Server 2019 和上一版的共存測試狀態。</span><span class="sxs-lookup"><span data-stu-id="63817-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="63817-114">在此狀態中，請務必測試並確定服務已啟動、每個網台都可以受系統管理，且用戶端可與目前及舊版使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="63817-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="63817-115">移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="63817-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="63817-116">通常，共存測試階段會存在於整個商務用 Skype Server 2019 的試驗測試中。</span><span class="sxs-lookup"><span data-stu-id="63817-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="63817-117">舊版使用者會移至商務用 Skype Server 2019 一段時間，以確保應用程式相容性和功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="63817-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="63817-118">在試驗測試之後，使用者和應用程式會移至商務用 Skype Server 2019 的實際執行版本，舊版集區和舊版本的應用程式就會終止。</span><span class="sxs-lookup"><span data-stu-id="63817-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
