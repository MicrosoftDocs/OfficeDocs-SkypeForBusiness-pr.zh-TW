---
title: Microsoft Teams 中的通話停駐和取回
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何在 Microsoft Teams 中使用通話停駐和取回來保留通話。
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278713"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="f8b27-103">Microsoft Teams 中的通話停駐和取回</span><span class="sxs-lookup"><span data-stu-id="f8b27-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="f8b27-104">通話保留和取回是一項功能，可讓使用者保留通話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="f8b27-105">當通話被停駐時，服務會產生唯一的代碼以用於呼叫取回。</span><span class="sxs-lookup"><span data-stu-id="f8b27-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="f8b27-106">接著，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="f8b27-107"> (請參閱在 Teams [中](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 將通話停駐，以尋找詳細資料。) </span><span class="sxs-lookup"><span data-stu-id="f8b27-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="f8b27-108">使用通話停駐的一些常見案例有：</span><span class="sxs-lookup"><span data-stu-id="f8b27-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="f8b27-109">總機會為在工廠工作的人打電話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="f8b27-110">然後，在公用電話系統上，接收者會宣告通話和代碼號碼。</span><span class="sxs-lookup"><span data-stu-id="f8b27-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="f8b27-111">接著，來電使用者就可以在工廠工廠拿起 Teams 電話，然後輸入代碼以取回通話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="f8b27-112">使用者將通話放在行動裝置上，因為裝置電池電力不足。</span><span class="sxs-lookup"><span data-stu-id="f8b27-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="f8b27-113">然後，使用者可以輸入代碼，從 Teams 電話機取回通話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="f8b27-114">支援代表會建立客戶通話的管道，並傳送公告給 Teams 頻道，讓專家取回通話並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="f8b27-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="f8b27-115">專家在 Teams 用戶端中輸入代碼以取回通話</span><span class="sxs-lookup"><span data-stu-id="f8b27-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="f8b27-116">若要停駐和取回通話，使用者必須是企業語音使用者，而且必須包含在通話停駐政策中。</span><span class="sxs-lookup"><span data-stu-id="f8b27-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="f8b27-117">通話停駐和取回僅適用于 [Teams 部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，商務用 Skype IP 電話不支援。</span><span class="sxs-lookup"><span data-stu-id="f8b27-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="f8b27-118">設定通話停駐和取回</span><span class="sxs-lookup"><span data-stu-id="f8b27-118">Configure call park and retrieve</span></span>

<span data-ttu-id="f8b27-119">您必須是 Teams 系統管理員，才能設定通話停駐和取回。</span><span class="sxs-lookup"><span data-stu-id="f8b27-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="f8b27-120">它預設為停用。</span><span class="sxs-lookup"><span data-stu-id="f8b27-120">It is disabled by default.</span></span> <span data-ttu-id="f8b27-121">您可以為使用者啟用通話，以及使用通話停駐政策建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="f8b27-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="f8b27-122">當您將相同的原則套用至一組使用者時，他們可以自行停駐和取回通話。</span><span class="sxs-lookup"><span data-stu-id="f8b27-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="f8b27-123">啟用通話停駐政策</span><span class="sxs-lookup"><span data-stu-id="f8b27-123">To enable a call park policy</span></span>

1. <span data-ttu-id="f8b27-124">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **通話公園政策**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="f8b27-125">在 [ **管理政策> 的選項卡** 上，按一下 **[新增**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="f8b27-126">為策略命名，然後將允許 **通話停駐切換** 為 **開啟**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![通話停駐政策設定螢幕擷取畫面](media/call-park-add-policy.png)

4. <span data-ttu-id="f8b27-128">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-128">Select **Save**.</span></span>

<span data-ttu-id="f8b27-129">您可以在清單中選取該策略，然後按一下編輯，以 **編輯該政策**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="f8b27-130">為了讓該策略能夠執行，必須將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f8b27-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="f8b27-131">您可以 [個別指派該政策給使用者](assign-policies.md) ，或將使用者指派給群組。</span><span class="sxs-lookup"><span data-stu-id="f8b27-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="f8b27-132">將通話部分政策指派給群組</span><span class="sxs-lookup"><span data-stu-id="f8b27-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="f8b27-133">在 [ **通話停駐點政策** 」 頁面上，按一下 [ **群組原則指派選項** > 的 **[新增群組**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="f8b27-134">搜尋您想要使用的群組，然後按一下 **[新增**。</span><span class="sxs-lookup"><span data-stu-id="f8b27-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="f8b27-135">選擇與其他群組作業比較的排名。</span><span class="sxs-lookup"><span data-stu-id="f8b27-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="f8b27-136">在 **選取一個策略** 下，選擇要指派給此群組的策略。</span><span class="sxs-lookup"><span data-stu-id="f8b27-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![公園政策圖像](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="f8b27-138">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="f8b27-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8b27-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8b27-139">Related topics</span></span>

[<span data-ttu-id="f8b27-140">在 Teams 中將通話停駐</span><span class="sxs-lookup"><span data-stu-id="f8b27-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="f8b27-141">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f8b27-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="f8b27-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b27-142">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="f8b27-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b27-143">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="f8b27-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="f8b27-144">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
