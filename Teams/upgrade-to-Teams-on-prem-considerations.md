---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533590"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="660e1-103">針對 IT 系統管理員使用商務用 Skype Server 內部部署之組織的升級考慮事項 &mdash;</span><span class="sxs-lookup"><span data-stu-id="660e1-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="660e1-104">本文將說明使用商務用 Skype Server 內部部署之組織的其他考慮事項。</span><span class="sxs-lookup"><span data-stu-id="660e1-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="660e1-105">本文是幾個描述 IT 系統管理員升級概念與實現的第四個專案。</span><span class="sxs-lookup"><span data-stu-id="660e1-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="660e1-106">概觀</span><span class="sxs-lookup"><span data-stu-id="660e1-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="660e1-107">升級方法</span><span class="sxs-lookup"><span data-stu-id="660e1-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="660e1-108">管理升級的工具</span><span class="sxs-lookup"><span data-stu-id="660e1-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="660e1-109">**使用商務用 Skype 內部部署之組織的其他考慮事項** (本文) </span><span class="sxs-lookup"><span data-stu-id="660e1-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="660e1-110">實施升級</span><span class="sxs-lookup"><span data-stu-id="660e1-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="660e1-111">公用交換電話網絡 (PSTN) 考慮</span><span class="sxs-lookup"><span data-stu-id="660e1-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="660e1-112">此外，下列文章說明重要的升級概念與共存行為：</span><span class="sxs-lookup"><span data-stu-id="660e1-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="660e1-113">團隊與商務用 Skype 的共存</span><span class="sxs-lookup"><span data-stu-id="660e1-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="660e1-114">共存模式-參考</span><span class="sxs-lookup"><span data-stu-id="660e1-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="660e1-115">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="660e1-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="660e1-116">商務用 Skype Server 內部部署的組織考慮事項</span><span class="sxs-lookup"><span data-stu-id="660e1-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="660e1-117">設定商務用 Skype 混合式版是遷移至 TeamsOnly 模式的先決條件。</span><span class="sxs-lookup"><span data-stu-id="660e1-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="660e1-118">雖然您可以在沒有混合式的孤島模式下使用小組，但在使用者從商務用 Skype 內部部署移至商務用 skype Online (使用 [move-csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)) 時，才無法進行。</span><span class="sxs-lookup"><span data-stu-id="660e1-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="660e1-119">如需詳細資訊，請參閱 [設定混合式連線性](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="660e1-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="660e1-120">如果您的組織有商務用 Skype Server，而且您還沒有設定混合式連線性，但您仍想要使用團隊來管理團隊功能，您必須使用具有 onmicrosoft.com 網域的系統管理帳戶。</span><span class="sxs-lookup"><span data-stu-id="660e1-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="660e1-121">擁有商務用 Skype 帳戶內部部署 (的小組使用者，尚未使用移動瀏覽器將其移到雲端，) 無法與任何商務用 Skype 使用者進行交互操作，也無法與外部使用者聯盟。</span><span class="sxs-lookup"><span data-stu-id="660e1-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="660e1-122">此功能只有在使用者移到雲端 (以孤島模式或 TeamsOnly 使用者) 時才可使用。</span><span class="sxs-lookup"><span data-stu-id="660e1-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="660e1-123">如果您有任何使用者使用商務用 Skype 帳戶內部部署，您就無法在租使用者層級指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="660e1-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="660e1-124">您必須先使用內部部署商務用 Skype 帳戶將所有使用者移至雲端，然後 `Move-CsUser` 停用 [混合式來完成到雲端的遷移](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="660e1-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="660e1-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` 如果偵測到的 lyncdiscover DNS 記錄指向 Office 365 以外的位置，就不會在租使用者層級運作。</span><span class="sxs-lookup"><span data-stu-id="660e1-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="660e1-126">您必須確保您的使用者能以正確的商務用 Skype 屬性正確地同步處理到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="660e1-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="660e1-127">這些屬性都是含 "msRTCSIP-" 的所有首碼。</span><span class="sxs-lookup"><span data-stu-id="660e1-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="660e1-128">如果使用者未正確地同步處理到 Azure AD，小組中的管理工具將無法管理這些使用者。</span><span class="sxs-lookup"><span data-stu-id="660e1-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="660e1-129"> (例如，除非正確同步處理這些屬性，否則您無法將團隊原則指派給內部部署使用者 ) 。如需詳細資訊，請參閱 [設定團隊與商務用 Skype 的 AZURE AD Connect](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)。</span><span class="sxs-lookup"><span data-stu-id="660e1-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="660e1-130">若要在混合式組織中建立新的 TeamsOnly 或商務用 Skype Online 使用者， *您必須先在內部部署中啟用商務用 Skype Server 中的使用者*，然後使用 move-csuser 將使用者從內部部署移至雲端。</span><span class="sxs-lookup"><span data-stu-id="660e1-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="660e1-131">首先，在內部部署中建立使用者，以確保任何其他剩餘的內部部署商務用 Skype 使用者都能傳送給新建立的使用者。</span><span class="sxs-lookup"><span data-stu-id="660e1-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="660e1-132">當所有使用者都在線上移動之後，就不再需要先在內部部署中啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="660e1-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="660e1-133">當使用者從內部部署移至雲端時，由該使用者組織的會議會遷移到商務用 Skype Online 或團隊中，視是否已指定-MoveToTeams 開關而定。</span><span class="sxs-lookup"><span data-stu-id="660e1-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="660e1-134">如果您想要在內部部署使用者的商務用 Skype 用戶端中顯示通知，您必須在內部部署工具集中使用 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="660e1-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="660e1-135">只有 NotifySfbUsers 參數與內部部署使用者有關。</span><span class="sxs-lookup"><span data-stu-id="660e1-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="660e1-136">內部部署使用者從 TeamsUpgradePolicy 的線上實例接收它們的模式。</span><span class="sxs-lookup"><span data-stu-id="660e1-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="660e1-137">請參閱授與 [授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)中的筆記。</span><span class="sxs-lookup"><span data-stu-id="660e1-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="660e1-138">2019在9月3日之後建立的任何新租使用者都會建立為 TeamsOnly 租使用者，除非組織已有內部部署的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="660e1-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="660e1-139">Microsoft 會使用 DNS 記錄來識別內部部署商務用 Skype 伺服器組織。</span><span class="sxs-lookup"><span data-stu-id="660e1-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="660e1-140">如果您的組織有內部部署商務用 Skype Server （沒有公用 DNS 專案），您必須致電 Microsoft 支援人員來降級新的租使用者。</span><span class="sxs-lookup"><span data-stu-id="660e1-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="660e1-141">相關連結</span><span class="sxs-lookup"><span data-stu-id="660e1-141">Related links</span></span>

[<span data-ttu-id="660e1-142">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="660e1-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="660e1-143">在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="660e1-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="660e1-144">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="660e1-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="660e1-145">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="660e1-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="660e1-146">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="660e1-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="660e1-147">使用會議遷移服務 (MMS) </span><span class="sxs-lookup"><span data-stu-id="660e1-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

