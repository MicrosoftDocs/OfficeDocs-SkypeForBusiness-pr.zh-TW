---
title: 設定通話分析Microsoft Teams
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
description: 設定每個使用者的通話分析，以找出和疑難排解Microsoft Teams品質問題。
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117131"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="94a09-103">設定通話分析Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94a09-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="94a09-104">做為Microsoft Teams系統管理員，您可以使用每個使用者的通話分析來疑難排解個別Teams通話品質與連接 **問題**。</span><span class="sxs-lookup"><span data-stu-id="94a09-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="94a09-105">若要充分利用通話分析，請設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="94a09-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="94a09-106">指派特殊支援角色給人員 ，例如技術支援人員，讓他們查看使用者的通話分析。</span><span class="sxs-lookup"><span data-stu-id="94a09-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="94a09-107">這些支援角色無法存取系統管理中心的其他Teams角色。</span><span class="sxs-lookup"><span data-stu-id="94a09-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="94a09-108">上傳 .tsv 或 .csv資料檔案，將建築物、網站和租使用者資訊新.csv分析。</span><span class="sxs-lookup"><span data-stu-id="94a09-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="94a09-109">當您準備好開始使用每個使用者的通話分析時，請閱讀使用每個使用者通話分析來疑難排解 [通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="94a09-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="94a09-110">給予支援和支援人員的許可權</span><span class="sxs-lookup"><span data-stu-id="94a09-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="94a09-111">作為系統管理員Teams，您可以完全存取所有使用者的通話分析資訊。</span><span class="sxs-lookup"><span data-stu-id="94a09-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="94a09-112">我們已建立一些Azure Active Directory角色，您可以將這些角色指派給支援人員及技術支援人員，這樣他們就可以存取每個使用者的通話分析 (，而不需要存取 Teams 系統管理中心) 。</span><span class="sxs-lookup"><span data-stu-id="94a09-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="94a09-113">將Teams **通訊支援專家** 角色指派給使用者，這些使用者應能有限地查看第 1 層支援 (使用者) 。</span><span class="sxs-lookup"><span data-stu-id="94a09-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="94a09-114">指派Teams **通訊支援工程師** 角色給需要完全存取每使用者通話分析的使用者， (第 2 層支援) 。</span><span class="sxs-lookup"><span data-stu-id="94a09-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="94a09-115">兩個角色都不得存取系統管理Teams中心。</span><span class="sxs-lookup"><span data-stu-id="94a09-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="94a09-116">若要瞭解每個角色的作用，請參閱每個角色Teams[角色的作用](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)？</span><span class="sxs-lookup"><span data-stu-id="94a09-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="94a09-117">若要進一Teams系統管理員角色，請參閱使用 Teams[系統管理員角色來管理Teams。](using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="94a09-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="94a09-118">若要瞭解如何在 Azure Active Directory 中指派系統管理員角色，請參閱在 Azure Active Directory[中查看Azure Active Directory。](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="94a09-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="94a09-119">若要瞭解如何在 Azure Active Directory 中指派系統管理角色，請參閱在 Azure Active Directory[中查看和指派Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)</span><span class="sxs-lookup"><span data-stu-id="94a09-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="94a09-120">Upload .tsv 或 .csv檔案來新增建築物、網站和租使用者資訊</span><span class="sxs-lookup"><span data-stu-id="94a09-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="94a09-121">您可以上傳檔案或 .tsv 檔案，將建築物、網站和租使用者資訊新增到每個使用者的通話分析.csv。</span><span class="sxs-lookup"><span data-stu-id="94a09-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="94a09-122">有了這些資訊，通話分析就可以將 IP 位址與實體位置進行比對。</span><span class="sxs-lookup"><span data-stu-id="94a09-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="94a09-123">系統管理員和技術支援人員可以使用這項資訊，協助發現通話問題的趨勢。</span><span class="sxs-lookup"><span data-stu-id="94a09-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="94a09-124">例如，為什麼同一棟大樓的使用者有類似的通話品質問題？</span><span class="sxs-lookup"><span data-stu-id="94a09-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="94a09-125">如果您是系統管理員或Teams商務用 Skype，您可以使用現有的租使用者和建立資料檔案，從 Teams 或 商務用 Skype 通話品質儀表板 (CQD) 。</span><span class="sxs-lookup"><span data-stu-id="94a09-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="94a09-126">首先，您從 CQD 下載檔案，然後上傳檔案以呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="94a09-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="94a09-127">若要下載現有的資料檔案，請前往系統管理中心Microsoft Teams  >  **通話品質儀表板**  >  **Upload 。**</span><span class="sxs-lookup"><span data-stu-id="94a09-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="94a09-128">在 [ **我的上傳清單上** ， **按一下** 您想要的檔案旁的下載。</span><span class="sxs-lookup"><span data-stu-id="94a09-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="94a09-129">若要上傳新檔案，請Microsoft Teams系統管理中心位置，然後選取 Upload或  >  \*\*\*\*\*\*取代位置資料\*\*。 </span><span class="sxs-lookup"><span data-stu-id="94a09-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="94a09-130">如果您要從頭開始建立 .tsv 或 .csv檔案，請參閱Upload[及建築物資料](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="94a09-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="94a09-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="94a09-131">Related topics</span></span>

[<span data-ttu-id="94a09-132">使用每個使用者的通話分析來疑難排解通話品質不佳的問題</span><span class="sxs-lookup"><span data-stu-id="94a09-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="94a09-133">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="94a09-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)