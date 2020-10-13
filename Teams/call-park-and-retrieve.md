---
title: 在 Microsoft 團隊中通話駐留與取回
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
description: 瞭解如何使用通話駐留及取回功能，在 Microsoft 團隊中保持通話。
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424579"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="28349-103">在 Microsoft 團隊中通話駐留與取回</span><span class="sxs-lookup"><span data-stu-id="28349-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="28349-104">通話駐留與取回功能可讓使用者在保留通話時撥打電話。</span><span class="sxs-lookup"><span data-stu-id="28349-104">Call park and retrieve is a feature that lets a user place a call on hold.</span></span> <span data-ttu-id="28349-105">當通話停用時，服務會產生唯一的呼叫檢索程式碼。</span><span class="sxs-lookup"><span data-stu-id="28349-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="28349-106">停用通話的使用者，或其他人可以將該程式碼與支援的 app 或裝置搭配使用，以取得通話。</span><span class="sxs-lookup"><span data-stu-id="28349-106">The user who parked the call or someone else can then use that code with a supported app or device to retrieve the call.</span></span> <span data-ttu-id="28349-107"> (請參閱 [在團隊中查看寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 以取得詳細資料。 ) </span><span class="sxs-lookup"><span data-stu-id="28349-107">(See see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) for details.)</span></span>

<span data-ttu-id="28349-108">使用通話駐留的一些常見案例如下：</span><span class="sxs-lookup"><span data-stu-id="28349-108">Some of the common scenarios for using call park are:</span></span>

- <span data-ttu-id="28349-109">[接待員] 負責在工廠中使用某個人的通話。</span><span class="sxs-lookup"><span data-stu-id="28349-109">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="28349-110">然後，接待員會宣佈通話，並將代碼編號放在公用位址系統上。</span><span class="sxs-lookup"><span data-stu-id="28349-110">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="28349-111">通話的使用者可以在工廠中挑選 [團隊電話]，然後輸入程式碼來檢索通話。</span><span class="sxs-lookup"><span data-stu-id="28349-111">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="28349-112">使用者在行動裝置上公園通話，因為裝置電池已用完電源。</span><span class="sxs-lookup"><span data-stu-id="28349-112">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="28349-113">然後，使用者可以輸入程式碼來從小組的手機中檢索通話。</span><span class="sxs-lookup"><span data-stu-id="28349-113">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="28349-114">支援代表會公園客戶通話，並在小組頻道上傳送公告，讓專家來取得通話並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="28349-114">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="28349-115">專家在 [團隊用戶端] 中輸入程式碼來檢索通話</span><span class="sxs-lookup"><span data-stu-id="28349-115">An expert enters the code in Teams clients to retrieve the call</span></span>

<span data-ttu-id="28349-116">若要寄存與取回通話，使用者必須是企業語音使用者，而且必須包含在通話寄存原則中。</span><span class="sxs-lookup"><span data-stu-id="28349-116">To park and retrieve calls, a user must be an Enterprise Voice user and and must be included in a call park policy.</span></span>

> [!NOTE]
> <span data-ttu-id="28349-117">通話駐留與取回功能僅適用于 [僅限小組中的部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ，且在商務用 Skype IP 手機上不受支援。</span><span class="sxs-lookup"><span data-stu-id="28349-117">Call park and retrieve is only available in [Teams Only deployment mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and is not supported on Skype for Business IP phones.</span></span>

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="28349-118">設定通話寄存與取回</span><span class="sxs-lookup"><span data-stu-id="28349-118">Configure call park and retrieve</span></span>

<span data-ttu-id="28349-119">您必須是團隊管理員，才能設定通話寄存與取回。</span><span class="sxs-lookup"><span data-stu-id="28349-119">You must be a Teams admin to configure call park and retrieve.</span></span> <span data-ttu-id="28349-120">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="28349-120">It is disabled by default.</span></span> <span data-ttu-id="28349-121">您可以為使用者啟用它，並使用通話駐留原則來建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="28349-121">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="28349-122">當您將相同的原則套用到一組使用者時，他們可以在自己的情況下寄存和取回通話。</span><span class="sxs-lookup"><span data-stu-id="28349-122">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span>

<span data-ttu-id="28349-123">啟用通話駐留原則</span><span class="sxs-lookup"><span data-stu-id="28349-123">To enable a call park policy</span></span>

1. <span data-ttu-id="28349-124">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。</span><span class="sxs-lookup"><span data-stu-id="28349-124">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="28349-125">在 [ **管理原則** ] 索引標籤上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="28349-125">On the **Manage policies** tab, click **Add**.</span></span>
3. <span data-ttu-id="28349-126">為原則命名，然後將 [ **允許通話駐留** ] 切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="28349-126">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>

    ![通話駐留原則設定的螢幕擷取畫面](media/call-park-add-policy.png)

4. <span data-ttu-id="28349-128">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="28349-128">Select **Save**.</span></span>

<span data-ttu-id="28349-129">您可以在清單中選取該原則，然後按一下 [ **編輯**] 來進行編輯。</span><span class="sxs-lookup"><span data-stu-id="28349-129">You can edit the policy by selecting it in the list and clicking **Edit**.</span></span>

<span data-ttu-id="28349-130">若要讓原則正常運作，必須將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="28349-130">In order for the policy to work, it must be assigned to users.</span></span> <span data-ttu-id="28349-131">您可以 [將原則單獨指派給使用者](assign-policies.md) ，或指派給群組。</span><span class="sxs-lookup"><span data-stu-id="28349-131">You can [assign the policy to users individually](assign-policies.md) or assign them to a group.</span></span>

<span data-ttu-id="28349-132">將呼叫部分原則指派給群組</span><span class="sxs-lookup"><span data-stu-id="28349-132">To assign a call part policy to a group</span></span>

1. <span data-ttu-id="28349-133">在 [ **通話駐留原則** ] 頁面的 [ **群組原則指派** ] 索引標籤上，按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="28349-133">On the **Call park policies** page, on the **Group policy assignment** tab, click **Add group**.</span></span>
2. <span data-ttu-id="28349-134">搜尋您要使用的群組，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="28349-134">Search for the group that you want to use, and then click **Add**.</span></span>
3. <span data-ttu-id="28349-135">選擇 [與其他群組指派] 相比的排名。</span><span class="sxs-lookup"><span data-stu-id="28349-135">Choose a rank compared to other group assignments.</span></span>
4. <span data-ttu-id="28349-136">在 [ **選取原則**] 下，選擇您要指派給此群組的原則。</span><span class="sxs-lookup"><span data-stu-id="28349-136">Under **Select a policy**, choose the policy that you want to assign this group to.</span></span>

    ![](media/call-park-assign-policy-to-group.png)

5. <span data-ttu-id="28349-137">按一下 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="28349-137">Click **Apply**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="28349-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="28349-138">Related topics</span></span>

[<span data-ttu-id="28349-139">在團隊中寄存通話</span><span class="sxs-lookup"><span data-stu-id="28349-139">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="28349-140">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="28349-140">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="28349-141">新-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="28349-141">New-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="28349-142">Set-CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="28349-142">Set-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[<span data-ttu-id="28349-143">授與 CsTeamsCallParkPolicy</span><span class="sxs-lookup"><span data-stu-id="28349-143">Grant-CsTeamsCallParkPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)