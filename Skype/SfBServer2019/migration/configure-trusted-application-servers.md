---
title: 設定信任的應用程式伺服器
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
description: 在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設定為商務用 Skype Server 2019 集區。 在混合式環境中，舊版集區和商務用 Skype Server 2019 集區會出現在下拉式清單中。 但不支援選取舊版集區。
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753943"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="ccd0c-105">設定信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="ccd0c-105">Configure trusted application servers</span></span>

<span data-ttu-id="ccd0c-106">在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設定為商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ccd0c-107">在混合式環境中，舊版集區和商務用 Skype Server 2019 集區會出現在下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="ccd0c-108">但不支援選取舊版集區。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ccd0c-109">如果您要遷移的是受信任的應用程式伺服器，也應該更新所使用的 UCMA 版本。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="ccd0c-110">如果您為商務用 Skype Server 2019 建立新的受信任應用程式集區，您應該將 UCMA 更新為商務用 Skype Server 2019 所隨附的版本或最新版本。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="ccd0c-111">在建立信任的應用程式伺服器時，選取商務用 Skype Server 2019 做為下一個躍點</span><span class="sxs-lookup"><span data-stu-id="ccd0c-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="ccd0c-112">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ccd0c-113">在左窗格中，以滑鼠右鍵按一下 [**信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式集**區</span><span class="sxs-lookup"><span data-stu-id="ccd0c-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="ccd0c-114">輸入信任的應用程式集區的 [**集區 FQDN** ]，並選取它將會是單一伺服器或多部伺服器。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="ccd0c-115">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="ccd0c-116">在 [**選取下一個躍點]** 頁面上，從清單中選取商務用 Skype Server 2019 前端集區。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="ccd0c-117">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="ccd0c-118">選取上方節點的**商務用 Skype 伺服器**，然後從 [**動作**] 功能表中選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="ccd0c-119">確認已成功建立**信任的應用程式集**區，且該集區與正確的前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="ccd0c-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

