---
title: 移轉撥入存取號碼
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
description: 若要將撥入存取號碼遷移至商務用 Skype Server 2019，必須執行 Move-CsApplicationEndpoint Cmdlet 以遷移連絡人物件。 在舊版安裝和商務用 Skype Server 2019 共存期間中，您在商務用 Skype Server 2019 中建立的撥入存取號碼，與您在舊版安裝中建立的撥入存取號碼類似，如本節所述。
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752695"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c41a4-104">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c41a4-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="c41a4-105">若要將撥入存取號碼遷移至商務用 Skype Server 2019，必須執行**Move-CsApplicationEndpoint** Cmdlet 以遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c41a4-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="c41a4-106">在舊版安裝和商務用 Skype Server 2019 共存期間中，您在商務用 Skype Server 2019 中建立的撥入存取號碼，與您在舊版安裝中建立的撥入存取號碼類似，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="c41a4-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="c41a4-107">您在舊版安裝中建立，但移至商務用 Skype Server 2019 的撥入存取號碼，或是在遷移之前、期間或遷移之後于商務用 Skype Server 2019 中建立的撥入存取號碼，都具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="c41a4-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="c41a4-108">不會出現在 Office 通訊伺服器 2007 R2 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="c41a4-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c41a4-109">會出現在舊版安裝會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="c41a4-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c41a4-110">會出現在商務用 Skype Server 2019 會議邀請和撥入存取號碼頁面上。</span><span class="sxs-lookup"><span data-stu-id="c41a4-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c41a4-111">無法在 Office 通訊伺服器 2007 R2 系統管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="c41a4-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="c41a4-112">可在舊版安裝控制台和舊版安裝管理命令介面中查看及修改。</span><span class="sxs-lookup"><span data-stu-id="c41a4-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="c41a4-113">可以在商務用 Skype Server 2019 控制台和商務用 Skype Server 2019 管理命令介面中查看及修改。</span><span class="sxs-lookup"><span data-stu-id="c41a4-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="c41a4-114">可以使用具有 Priority 參數的 Set-CsDialinConferencingAccessNumber Cmdlet，在地區內重新排序。</span><span class="sxs-lookup"><span data-stu-id="c41a4-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="c41a4-115">您必須完成將指向舊版安裝集區的撥入存取號碼遷移，再解除委任舊版安裝集區。</span><span class="sxs-lookup"><span data-stu-id="c41a4-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="c41a4-116">如果您未完成撥入存取號碼遷移（如下列程式所述），則對存取號碼的來電將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c41a4-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c41a4-117">您必須先執行此程式，再解除委任舊版安裝集區。</span><span class="sxs-lookup"><span data-stu-id="c41a4-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="c41a4-118">建議您在網路使用量很低時移動撥入存取號碼，以防出現短時間的服務中斷。</span><span class="sxs-lookup"><span data-stu-id="c41a4-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="c41a4-119">識別並移動撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="c41a4-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="c41a4-120">啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [**商務用 skype 伺服器管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="c41a4-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c41a4-121">若要將每個撥入存取號碼移至主控于商務用 Skype Server 2019 的集區，請從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="c41a4-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="c41a4-122">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c41a4-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="c41a4-123">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="c41a4-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="c41a4-124">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c41a4-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="c41a4-125">確認您要遷移之舊版安裝集區的撥入存取號碼仍未保留。</span><span class="sxs-lookup"><span data-stu-id="c41a4-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c41a4-126">當所有撥入存取號碼指向商務用 Skype Server 2019 集區時，您就可以解除委任舊版安裝集區。</span><span class="sxs-lookup"><span data-stu-id="c41a4-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c41a4-127">使用商務用 Skype Server 控制台驗證撥入存取號碼遷移</span><span class="sxs-lookup"><span data-stu-id="c41a4-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c41a4-128">從指派給**CsUserAdministrator**角色或**CsAdministrator**角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c41a4-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="c41a4-129">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c41a4-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c41a4-130">在左側導覽列中，按一下 **[會議]**。</span><span class="sxs-lookup"><span data-stu-id="c41a4-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="c41a4-131">按一下 [**撥入存取號碼**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c41a4-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="c41a4-132">確認所有撥入存取號碼都已遷移到主控于商務用 Skype Server 2019 的集區。</span><span class="sxs-lookup"><span data-stu-id="c41a4-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c41a4-133">使用商務用 Skype Server 管理命令介面來驗證撥入存取號碼遷移</span><span class="sxs-lookup"><span data-stu-id="c41a4-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c41a4-134">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="c41a4-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="c41a4-135">若要傳回已遷移的所有電話撥入式會議存取號碼，請從命令列執行：</span><span class="sxs-lookup"><span data-stu-id="c41a4-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="c41a4-136">確認所有撥入存取號碼都已遷移到主控于商務用 Skype Server 2019 的集區。</span><span class="sxs-lookup"><span data-stu-id="c41a4-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


