---
title: 遷移撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 將撥入存取號碼移植到商務用 Skype Server 2019 需要執行 CsApplicationEndpoint Cmdlet 來遷移連絡人物件。 在舊版安裝與商務用 Skype Server 2019 的共存期間, 您在商務用 Skype Server 2019 中建立的撥入存取號碼與您在舊版安裝中建立的撥入存取號碼類似, 如以下所述。頂部.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238731"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="e6d8c-104">遷移撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="e6d8c-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="e6d8c-105">將撥入存取號碼移植到商務用 Skype Server 2019 需要執行**CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="e6d8c-106">在舊版安裝與商務用 Skype Server 2019 的共存期間, 您在商務用 Skype Server 2019 中建立的撥入存取號碼與您在舊版安裝中建立的撥入存取號碼類似, 如以下所述。頂部.</span><span class="sxs-lookup"><span data-stu-id="e6d8c-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="e6d8c-107">您在舊版安裝中建立的撥入號碼, 但移動到商務用 Skype Server 2019, 或是在遷移期間或之後在商務用 Skype Server 2019 中建立的電話, 都具有下列特性:</span><span class="sxs-lookup"><span data-stu-id="e6d8c-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="e6d8c-108">不會出現在 Office 通訊伺服器 2007 R2 會議邀請和 [撥入存取號碼] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e6d8c-109">出現在舊版 [安裝會議邀請] 和 [撥入存取號碼] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e6d8c-110">出現在商務用 Skype Server 2019 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e6d8c-111">無法在 Office 通訊伺服器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="e6d8c-112">您可以在舊版安裝控制台和舊版安裝管理命令介面中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="e6d8c-113">您可以在商務用 Skype Server 2019 [控制台] 和商務用 Skype Server 2019 管理命令介面中查看及修改。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="e6d8c-114">可在區域內使用 CsDialinConferencingAccessNumber Cmdlet 與 Priority 參數重新排序。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="e6d8c-115">您必須先完成指向舊版安裝池中的撥入存取號碼的遷移, 才能停止舊版安裝區。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="e6d8c-116">如果您沒有完成撥入存取號碼遷移, 請參閱以下程式中所述的接入號碼來電將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6d8c-117">您必須先執行此程式, 然後才能解除舊版安裝池。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="e6d8c-118">我們建議您在網路使用量較低時移動撥入存取號碼 (如果有短暫的服務停機時間)。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="e6d8c-119">識別及移動撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="e6d8c-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="e6d8c-120">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e6d8c-121">若要將每個撥入存取號碼移至託管于商務用 Skype Server 2019 的 pool, 請從命令列執行:</span><span class="sxs-lookup"><span data-stu-id="e6d8c-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="e6d8c-122">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="e6d8c-123">在左側導覽列中, 按一下 [**會議**]。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="e6d8c-124">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="e6d8c-125">確認您要從中遷移的舊版安裝池中仍沒有任何撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6d8c-126">當所有撥入存取號碼都指向商務用 Skype Server 2019 池時, 您就可以開始解除舊版安裝區。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e6d8c-127">使用商務用 Skype Server [控制台] 驗證撥入存取號碼遷移</span><span class="sxs-lookup"><span data-stu-id="e6d8c-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e6d8c-128">從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="e6d8c-129">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e6d8c-130">在左側導覽列中, 按一下 [**會議**]。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="e6d8c-131">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="e6d8c-132">確認所有撥入存取號碼都已遷移至託管于商務用 Skype Server 2019 的池中。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e6d8c-133">使用商務用 Skype Server Management Shell 來驗證撥入存取號碼遷移</span><span class="sxs-lookup"><span data-stu-id="e6d8c-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e6d8c-134">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="e6d8c-135">若要從命令列中傳回已轉移的所有電話撥入式會議存取電話號碼, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="e6d8c-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="e6d8c-136">確認所有撥入存取號碼都已遷移至託管于商務用 Skype Server 2019 的池中。</span><span class="sxs-lookup"><span data-stu-id="e6d8c-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


