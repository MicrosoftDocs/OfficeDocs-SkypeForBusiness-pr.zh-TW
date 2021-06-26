---
title: 在通話中呼叫Microsoft Teams
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
description: 瞭解如何在通話中使用通話保留和Microsoft Teams。
ms.openlocfilehash: fb60e09148f2b96ce9b4d059d7d112c817239822
ms.sourcegitcommit: 355c7858b98518f6a922110390c51eb7e2cd6690
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "53147181"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="4d722-103">在通話中呼叫Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4d722-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="4d722-104">呼叫保留和取回功能可讓使用者保留通話。</span><span class="sxs-lookup"><span data-stu-id="4d722-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="4d722-105">當通話被停駐時，服務會產生唯一的通話取回程序代碼。</span><span class="sxs-lookup"><span data-stu-id="4d722-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="4d722-106">之後，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。</span><span class="sxs-lookup"><span data-stu-id="4d722-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="4d722-107"> (請參閱[將通話Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)中，以) </span><span class="sxs-lookup"><span data-stu-id="4d722-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="4d722-108">使用呼叫停駐的一些常見案例有：</span><span class="sxs-lookup"><span data-stu-id="4d722-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="4d722-109">接待員會為在工廠工作的人打電話。</span><span class="sxs-lookup"><span data-stu-id="4d722-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="4d722-110">然後，接待員在公用電話系統上宣佈通話和代碼號碼。</span><span class="sxs-lookup"><span data-stu-id="4d722-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="4d722-111">接著，通話使用者可以在工廠Teams接聽電話，然後輸入代碼以取回通話。</span><span class="sxs-lookup"><span data-stu-id="4d722-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="4d722-112">使用者將通話放在行動裝置上，因為裝置電池電力不足。</span><span class="sxs-lookup"><span data-stu-id="4d722-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="4d722-113">然後，使用者可以輸入代碼，從電話機Teams通話。</span><span class="sxs-lookup"><span data-stu-id="4d722-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="4d722-114">支援代表會將客戶電話放在Teams頻道上傳送公告，讓專家取回來電並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="4d722-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="4d722-115">專家在用戶端中輸入Teams以取回通話</span><span class="sxs-lookup"><span data-stu-id="4d722-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="4d722-116">若要將通話停駐和取回，使用者必須是企業語音使用者，且必須包含在通話駐用策略中。</span><span class="sxs-lookup"><span data-stu-id="4d722-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4d722-117">呼叫停駐和Teams只能在部署模式中[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)使用，IP 電話商務用 Skype不支援。</span><span class="sxs-lookup"><span data-stu-id="4d722-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="4d722-118">設定呼叫停駐和取回</span><span class="sxs-lookup"><span data-stu-id="4d722-118">Configure call park and retrieve</span></span>

<span data-ttu-id="4d722-119">您必須是管理員Teams才能設定呼叫駐位和取回。</span><span class="sxs-lookup"><span data-stu-id="4d722-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="4d722-120">它預設為停用。</span><span class="sxs-lookup"><span data-stu-id="4d722-120">It is disabled by default.</span></span> <span data-ttu-id="4d722-121">您可以為使用者啟用它，然後使用呼叫停駐策略建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="4d722-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="4d722-122">當您將相同的原則套用至一組使用者時，他們可以在使用者之間停駐和取回通話。</span><span class="sxs-lookup"><span data-stu-id="4d722-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="4d722-123">呼叫代答號碼的範圍已預先定義為 10-99，且無法修改。</span><span class="sxs-lookup"><span data-stu-id="4d722-123">The range of call pickup numbers is predefined to be from 10-99 and cannot be modified.</span></span> <span data-ttu-id="4d722-124">第一個已停駐的通話會呈現 10 的代答碼，下一個已停駐的通話會呈現 11 的代答碼，等等。</span><span class="sxs-lookup"><span data-stu-id="4d722-124">The first parked call will be rendered a pickup code of 10, the next parked call will be rendered a pickup code of 11, etc.</span></span> <span data-ttu-id="4d722-125">直到 99 呈現為代答程式碼。</span><span class="sxs-lookup"><span data-stu-id="4d722-125">until 99 is rendered as a pickup code.</span></span> <span data-ttu-id="4d722-126">之後，呈現的取件代碼會再次從 10 開始。</span><span class="sxs-lookup"><span data-stu-id="4d722-126">After which, the rendered pickup codes start over from 10 once again.</span></span>  <span data-ttu-id="4d722-127">如果超過 89 個使用中的保留通話，則呈現的代答碼會持續遞增到 99 以上，如此一來，第 90 個有效保留的通話會呈現 100 個代答程式碼，第 91 個使用中的保留通話會呈現 101 的代答碼。</span><span class="sxs-lookup"><span data-stu-id="4d722-127">If there are more than 89 active parked calls, the rendered pickup codes will keep incrementing beyond 99 such that the 90th active parked call would be rendered 100 for a pickup code, the 91st active parked call would be rendered a pickup code of 101.</span></span>

<span data-ttu-id="4d722-128">若要啟用通話停駐策略</span><span class="sxs-lookup"><span data-stu-id="4d722-128">To enable a call park policy</span></span>

1. <span data-ttu-id="4d722-129">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **通話停駐區政策**。</span><span class="sxs-lookup"><span data-stu-id="4d722-129">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="4d722-130">在 [ **管理原則>** 選項卡上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="4d722-130">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="4d722-131">為策略命名，然後將允許 **通話停駐切換到\*\*\*\*開啟**。</span><span class="sxs-lookup"><span data-stu-id="4d722-131">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![通話停駐策略設定螢幕擷取畫面](media/call-park-add-policy.png)

4. <span data-ttu-id="4d722-133">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="4d722-133">Select **Save**.</span></span>

<span data-ttu-id="4d722-134">您可以在清單中選取該策略，然後按一下 編輯 來 **編輯。**</span><span class="sxs-lookup"><span data-stu-id="4d722-134">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="4d722-135">為了讓該策略能夠執行，必須將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="4d722-135">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="4d722-136">您可以 [個別指派該策略](assign-policies.md) 給使用者，或將使用者指派給群組。</span><span class="sxs-lookup"><span data-stu-id="4d722-136">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="4d722-137">將呼叫停駐策略指派給群組</span><span class="sxs-lookup"><span data-stu-id="4d722-137">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="4d722-138">在 [ **通話停駐點政策」** 頁面上，按一下 [ **群群組原則指派** > 的 [新增群組> 的 **[新增群組**> 。</span><span class="sxs-lookup"><span data-stu-id="4d722-138">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="4d722-139">搜尋您想要使用的群組，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="4d722-139">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="4d722-140">選擇與其他群組作業比較的排名。</span><span class="sxs-lookup"><span data-stu-id="4d722-140">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="4d722-141">在 **選取策略下**，選擇要指派此群組的政策。</span><span class="sxs-lookup"><span data-stu-id="4d722-141">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Park policies 影像](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="4d722-143">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="4d722-143">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d722-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="4d722-144">Related topics</span></span>

[<span data-ttu-id="4d722-145">將通話Teams</span><span class="sxs-lookup"><span data-stu-id="4d722-145">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="4d722-146">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="4d722-146">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="4d722-147">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="4d722-147">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="4d722-148">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="4d722-148">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="4d722-149">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="4d722-149">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
