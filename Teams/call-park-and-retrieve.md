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
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197578"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="13db8-103">在通話中呼叫Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="13db8-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="13db8-104">呼叫保留和取回功能可讓使用者保留通話。</span><span class="sxs-lookup"><span data-stu-id="13db8-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="13db8-105">當通話被停駐時，服務會產生唯一的通話取回程序代碼。</span><span class="sxs-lookup"><span data-stu-id="13db8-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="13db8-106">之後，將通話停駐的使用者或其他人就可以在支援的 App 或裝置上使用該代碼來取回通話。</span><span class="sxs-lookup"><span data-stu-id="13db8-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="13db8-107"> (請參閱[將通話Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)中，以) </span><span class="sxs-lookup"><span data-stu-id="13db8-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="13db8-108">使用呼叫停駐的一些常見案例有：</span><span class="sxs-lookup"><span data-stu-id="13db8-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="13db8-109">接待員會為在工廠工作的人打電話。</span><span class="sxs-lookup"><span data-stu-id="13db8-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="13db8-110">然後，接待員在公用電話系統上宣佈通話和代碼號碼。</span><span class="sxs-lookup"><span data-stu-id="13db8-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="13db8-111">接著，負責通話的使用者可以在工廠Teams電話，然後輸入代碼以取回通話。</span><span class="sxs-lookup"><span data-stu-id="13db8-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="13db8-112">使用者將通話放在行動裝置上，因為裝置電池電力不足。</span><span class="sxs-lookup"><span data-stu-id="13db8-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="13db8-113">然後，使用者可以輸入代碼，從電話機Teams通話。</span><span class="sxs-lookup"><span data-stu-id="13db8-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="13db8-114">支援代表會將客戶電話放在Teams頻道上傳送公告，讓專家取回來電並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="13db8-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="13db8-115">專家在用戶端中輸入Teams以取回通話</span><span class="sxs-lookup"><span data-stu-id="13db8-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="13db8-116">若要將通話停駐和取回，使用者必須是企業語音使用者，且必須包含在通話駐用策略中。</span><span class="sxs-lookup"><span data-stu-id="13db8-116">To park and retrieve calls, a user must be an Enterprise Voice user and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="13db8-117">呼叫停駐和Teams只能在部署模式中[](teams-and-skypeforbusiness-coexistence-and-interoperability.md)使用，IP 電話商務用 Skype不支援。</span><span class="sxs-lookup"><span data-stu-id="13db8-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="13db8-118">設定呼叫停駐和取回</span><span class="sxs-lookup"><span data-stu-id="13db8-118">Configure call park and retrieve</span></span>

<span data-ttu-id="13db8-119">您必須是管理員Teams才能設定呼叫駐位和取回。</span><span class="sxs-lookup"><span data-stu-id="13db8-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="13db8-120">它預設為停用。</span><span class="sxs-lookup"><span data-stu-id="13db8-120">It is disabled by default.</span></span> <span data-ttu-id="13db8-121">您可以為使用者啟用它，然後使用呼叫停駐策略建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="13db8-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="13db8-122">當您將相同的原則套用至一組使用者時，他們可以在使用者之間停駐和取回通話。</span><span class="sxs-lookup"><span data-stu-id="13db8-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="13db8-123">若要啟用通話停駐策略</span><span class="sxs-lookup"><span data-stu-id="13db8-123">To enable a call park policy</span></span>

1. <span data-ttu-id="13db8-124">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **通話停駐區政策**。</span><span class="sxs-lookup"><span data-stu-id="13db8-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="13db8-125">在 [ **管理原則>** 選項卡上，按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="13db8-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="13db8-126">為策略命名，然後將允許 **通話停駐切換到\*\*\*\*開啟**。</span><span class="sxs-lookup"><span data-stu-id="13db8-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![通話停駐策略設定螢幕擷取畫面](media/call-park-add-policy.png)

4. <span data-ttu-id="13db8-128">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="13db8-128">Select **Save**.</span></span>

<span data-ttu-id="13db8-129">您可以在清單中選取該策略，然後按一下編輯來 **編輯。**</span><span class="sxs-lookup"><span data-stu-id="13db8-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="13db8-130">為了讓該策略能夠執行，必須將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="13db8-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="13db8-131">您可以 [個別指派該策略](assign-policies.md) 給使用者，或將使用者指派給群組。</span><span class="sxs-lookup"><span data-stu-id="13db8-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="13db8-132">將呼叫停駐策略指派給群組</span><span class="sxs-lookup"><span data-stu-id="13db8-132">To assign a call park policy to a group</span></span>

1. <span data-ttu-id="13db8-133">在 [ **通話停駐點政策」** 頁面上，按一下 [ **群群組原則指派** > 的 [新增群組> 的 **[新增群組**> 。</span><span class="sxs-lookup"><span data-stu-id="13db8-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="13db8-134">搜尋您想要使用的群組，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="13db8-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="13db8-135">選擇與其他群組作業比較的排名。</span><span class="sxs-lookup"><span data-stu-id="13db8-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="13db8-136">在 **選取策略下**，選擇要指派此群組的政策。</span><span class="sxs-lookup"><span data-stu-id="13db8-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![Park policies 影像](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="13db8-138">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="13db8-138">Select **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13db8-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="13db8-139">Related topics</span></span>

[<span data-ttu-id="13db8-140">將通話Teams</span><span class="sxs-lookup"><span data-stu-id="13db8-140">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="13db8-141">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="13db8-141">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="13db8-142">New-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="13db8-142">New-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="13db8-143">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="13db8-143">Set-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="13db8-144">Grant-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="13db8-144">Grant-CsTeamsCallParkPolicy</span></span>](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)