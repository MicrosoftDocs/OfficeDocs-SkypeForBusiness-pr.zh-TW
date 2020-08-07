---
title: 設定 Microsoft 團隊的呼叫分析
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: 設定每個使用者的呼叫分析，以找出並解決 Microsoft 團隊通話品質問題。
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581104"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="2a599-103">設定 Microsoft 團隊的呼叫分析</span><span class="sxs-lookup"><span data-stu-id="2a599-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="2a599-104">做為 Microsoft 團隊管理員，您可以使用每個使用者的呼叫分析來疑難排解小組針對**個別使用者**呼叫品質與連線問題。</span><span class="sxs-lookup"><span data-stu-id="2a599-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="2a599-105">若要充分利用呼叫分析，請設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="2a599-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="2a599-106">將特殊支援角色指派給人員（例如支援者的 agent），讓他們能夠查看使用者的呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="2a599-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="2a599-107">這些支援角色無法存取其他團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2a599-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="2a599-108">透過上傳 tsv 或 .csv 資料檔，將建築物、網站和租使用者資訊新增至每個使用者呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="2a599-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="2a599-109">當您準備好要開始使用每個使用者的呼叫分析時，請閱讀[使用每個使用者的呼叫分析，以解決通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="2a599-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="2a599-110">授與支援人員及技術支援人員的許可權</span><span class="sxs-lookup"><span data-stu-id="2a599-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="2a599-111">就團隊管理員而言，您擁有所有使用者的呼叫分析資訊的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="2a599-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="2a599-112">我們已建立一些專用的 Azure Active Directory 角色，您可以將它指派給支援人員和支援人員的代理，讓他們也能存取每位使用者的呼叫分析 (，而不需存取團隊系統管理員中心的其他部分) 。</span><span class="sxs-lookup"><span data-stu-id="2a599-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="2a599-113">將**團隊通訊支援專家**角色指派給應該擁有有限的每使用者呼叫分析視圖的使用者， (第1層支援) 。</span><span class="sxs-lookup"><span data-stu-id="2a599-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="2a599-114">指派**團隊通訊支援工程師**角色給需要對每位使用者呼叫分析進行完整存取的使用者， (第2層支援) 。</span><span class="sxs-lookup"><span data-stu-id="2a599-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="2a599-115">兩個角色都無法存取其他團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="2a599-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="2a599-116">若要瞭解這些角色的作用，請閱讀[每個團隊支援角色的功能是什麼](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？</span><span class="sxs-lookup"><span data-stu-id="2a599-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="2a599-117">如需有關團隊管理員角色的詳細資訊，請參閱[使用團隊管理員角色管理團隊](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2a599-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="2a599-118">若要瞭解如何在 Azure Active Directory 中指派系統管理員角色，請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="2a599-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="2a599-119">若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參閱[在 Azure Active directory 中查看和指派角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="2a599-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="2a599-120">上傳. tsv 或 .csv 檔案，以新增建築物、網站和租使用者資訊</span><span class="sxs-lookup"><span data-stu-id="2a599-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="2a599-121">您可以透過上傳 .csv 或 tsv 檔案，將建築物、網站和租使用者資訊新增至每個使用者呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="2a599-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="2a599-122">在所有這些資訊的情況下，呼叫分析可以將 IP 位址對應至物理位置。</span><span class="sxs-lookup"><span data-stu-id="2a599-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="2a599-123">系統管理員和支援人員都可以使用這項資訊來協助找出通話問題的趨勢。</span><span class="sxs-lookup"><span data-stu-id="2a599-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="2a599-124">例如，為什麼同一個建築物中的使用者有類似的通話品質問題？</span><span class="sxs-lookup"><span data-stu-id="2a599-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="2a599-125">如果您是團隊或商務用 Skype 系統管理員，您可以使用現有的租使用者，並從 [小組] 或 [商務用 Skype 通話品質] 儀表板中建立資料檔， (CQD) ]。</span><span class="sxs-lookup"><span data-stu-id="2a599-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="2a599-126">首先，您要從 CQD 下載檔案，然後將檔案上傳到 [呼叫分析]。</span><span class="sxs-lookup"><span data-stu-id="2a599-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="2a599-127">若要下載現有的資料檔，請移至**Microsoft 團隊系統管理中心**的  >  **通話品質儀表板**  >  **[立即上傳**]。</span><span class="sxs-lookup"><span data-stu-id="2a599-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="2a599-128">在 [**我**的上傳] 清單中，按一下您想要的檔案旁的 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="2a599-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="2a599-129">若要上傳新檔案，請移至**Microsoft 團隊系統管理中心**  >  **位置**，然後選取 **[上傳位置資料**] 或 [**取代位置資料**]。</span><span class="sxs-lookup"><span data-stu-id="2a599-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="2a599-130">如果您要從頭開始建立 tsv 或 .csv 檔案，請參閱[上傳租使用者及組建資料](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2a599-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2a599-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a599-131">Related topics</span></span>

[<span data-ttu-id="2a599-132">使用每位使用者通話分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="2a599-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="2a599-133">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="2a599-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
