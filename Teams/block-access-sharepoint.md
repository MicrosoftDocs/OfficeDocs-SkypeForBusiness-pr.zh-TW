---
title: 封鎖特定使用者對 SharePoint 的存取權
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何封鎖特定使用者對 SharePoint 的存取權
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135927"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="b9683-103">封鎖特定使用者對 SharePoint 的存取權</span><span class="sxs-lookup"><span data-stu-id="b9683-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="b9683-104">在 Microsoft 365 的 SharePoint 中，將任何條件式存取 (CA) 原則，也會套用至小組。</span><span class="sxs-lookup"><span data-stu-id="b9683-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="b9683-105">不過，某些組織想要封鎖 SharePoint 檔案的存取權 (上傳、下載、查看、編輯、建立) 但仍允許員工在未受管理的裝置上使用小組桌面、行動裝置和 web 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9683-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="b9683-106">在 CA 原則規則底下，封鎖 Sharepoint 也會導致封鎖小組。</span><span class="sxs-lookup"><span data-stu-id="b9683-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="b9683-107">本文說明如何解決這項限制，並允許員工繼續使用團隊，同時完全封鎖對儲存在 SharePoint 中的檔案的存取權。</span><span class="sxs-lookup"><span data-stu-id="b9683-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="b9683-108">受管理的裝置上的封鎖或限制存取依賴于 Azure AD 條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="b9683-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="b9683-109">瞭解 [AZURE AD 授權](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="b9683-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="b9683-110">如需 Azure AD 中的條件式存取權概覽，請參閱 [Azure Active Directory 中的條件式存取](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)。</span><span class="sxs-lookup"><span data-stu-id="b9683-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="b9683-111">如需建議的 SharePoint Online 存取原則的相關資訊，請參閱 [保護 sharepoint 網站和檔案的原則建議](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="b9683-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="b9683-112">如果您在未受管理的裝置上限制存取，受管理的裝置上的使用者必須使用其中一個 [受支援的作業系統和瀏覽器混合](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)，否則它們也會有有限的存取權。</span><span class="sxs-lookup"><span data-stu-id="b9683-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="b9683-113">您可以封鎖或限制存取：</span><span class="sxs-lookup"><span data-stu-id="b9683-113">You can block or limit access for:</span></span>

- <span data-ttu-id="b9683-114">組織中的使用者或只有部分使用者或安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b9683-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="b9683-115">組織中的所有網站或只在部分網站中。</span><span class="sxs-lookup"><span data-stu-id="b9683-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="b9683-116">當存取權封鎖時，使用者會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b9683-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="b9683-117">封鎖存取可協助提供安全性並保護安全的資料。</span><span class="sxs-lookup"><span data-stu-id="b9683-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="b9683-118">當存取權封鎖時，使用者會看到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b9683-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="b9683-119">開啟 SharePoint 系統 [管理中心](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)。</span><span class="sxs-lookup"><span data-stu-id="b9683-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="b9683-120">展開 [**原則**  >  **存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="b9683-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="b9683-121">在 [ **未管理的裝置** ] 區段中，選取 [ **封鎖存取** ] 並選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9683-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![原則的 [未受管理的裝置] 區段](media/no-sharepoint-access1.png)

4. <span data-ttu-id="b9683-123">開啟 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 入口網站，然後流覽至 [ **條件式存取原則**]。</span><span class="sxs-lookup"><span data-stu-id="b9683-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="b9683-124">您會看到 SharePoint 建立了一個類似這個範例的新原則：</span><span class="sxs-lookup"><span data-stu-id="b9683-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![名為「使用 app 強制限制的瀏覽器存取」的新原則](media/no-sharepoint-access2.png)

5. <span data-ttu-id="b9683-126">將原則更新為僅以特定使用者或群組為目標。</span><span class="sxs-lookup"><span data-stu-id="b9683-126">Update the policy to target only specific users or a group.</span></span>

    ![[Sharepoint 系統管理中心] 醒目提示 [選取使用者] 區段。](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="b9683-128">設定此原則將會切斷您對 SharePoint 系統管理入口網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="b9683-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="b9683-129">建議您設定排除原則，並選取全域和 SharePoint 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b9683-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="b9683-130">確認只選取 [SharePoint] 作為 [目標雲端] App</span><span class="sxs-lookup"><span data-stu-id="b9683-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![已選取 [Sharepoint] 作為目標 app。](media/no-sharepoint-access3.png)

7. <span data-ttu-id="b9683-132">更新 **條件** 以包含桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9683-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![桌面和行動裝置 app 已醒目提示。](media/no-sharepoint-access4.png)

8. <span data-ttu-id="b9683-134">確認已啟用 **[授與存取權** ]</span><span class="sxs-lookup"><span data-stu-id="b9683-134">Make sure that **Grant access** is enabled</span></span>

    ![已啟用 [授與存取權]。](media/no-sharepoint-access5.png)

9. <span data-ttu-id="b9683-136">請確定已啟用 [ **使用 app 強制性限制** ]。</span><span class="sxs-lookup"><span data-stu-id="b9683-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="b9683-137">啟用您的原則，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b9683-137">Enable your policy and select **Save**.</span></span>

    ![已啟用應用程式強制執行限制。](media/no-sharepoint-access6.png)

<span data-ttu-id="b9683-139">若要測試原則，您必須從任何用戶端（例如團隊桌面應用程式或商務用 OneDrive 同步處理用戶端）登出，然後再次登入，以查看原則是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="b9683-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="b9683-140">如果您的存取權遭到封鎖，就會在小組中看到一則訊息，指出該專案可能不存在。</span><span class="sxs-lookup"><span data-stu-id="b9683-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![[找不到專案] 訊息。](media/access-denied-sharepoint.png)

<span data-ttu-id="b9683-142">在 Sharepoint 中，您會收到「拒絕存取」的訊息。</span><span class="sxs-lookup"><span data-stu-id="b9683-142">In Sharepoint, you'll receive an access denied message.</span></span>

![[拒絕存取] 訊息。](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="b9683-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="b9683-144">Related topics</span></span>

[<span data-ttu-id="b9683-145">在 SharePoint 中控制非託管裝置的存取權</span><span class="sxs-lookup"><span data-stu-id="b9683-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
