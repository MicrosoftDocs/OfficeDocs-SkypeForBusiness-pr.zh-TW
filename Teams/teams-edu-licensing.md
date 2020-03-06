---
title: 適用於 Microsoft Teams 教育版管理員的資源
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版的授權逐步解說。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b653acbe18d2247ccbf64a523fd237ca1415414
ms.sourcegitcommit: ac811017d54a55f39ecc0e3a66a883d9e027ce68
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547936"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="ac0b1-103">指派 Microsoft Teams 教育版授權</span><span class="sxs-lookup"><span data-stu-id="ac0b1-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="ac0b1-104">Microsoft Teams 是將交談、內容和應用程式集中在同一個位置的數位中心。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="ac0b1-105">因為它是在 Office 365 的基礎上建立，學校可以與他們熟悉的 Office 應用程式和服務整合。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="ac0b1-106">您的機構可以使用 Microsoft Teams 建立共同作業教室、在專業學習社群中交流，以及與學校教職員溝通，這些都來自 Office 365 教育版的單一體驗。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="ac0b1-107">若要開始使用，IT 系統管理員必須使用 Microsoft 365 系統管理中心[為您的學校啟用 Microsoft Teams](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="ac0b1-108">完成之後，您必須將授權指派給使用者帳戶，您的教職員、員工和學生才能存取 Office 365 服務，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="ac0b1-109">您可以採用個別方式或透過群組成員資格，將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="ac0b1-110">本文將逐步引導您瞭解如何透過 Microsoft 365 系統管理中心，將 Office 365 授權指派給個別或一小部分的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="ac0b1-111">若要透過群組成員資格自動指派授權，請參閱我們其中一篇支援文章：</span><span class="sxs-lookup"><span data-stu-id="ac0b1-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- <span data-ttu-id="ac0b1-112">[Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="ac0b1-112">[Office 365 Powershell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span></span>
- <span data-ttu-id="ac0b1-113">[Active Directory 中的群組型授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) (部分機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="ac0b1-113">[Group-based Licensing in Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>

<span data-ttu-id="ac0b1-114">您可以在 [授權]\*\*\*\* 頁面或 [作用中使用者]\*\*\*\* 頁面上將授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="ac0b1-115">所使用的方法取決於您要指派產品授權給特定使用者，還是要將使用者授權指派給特定產品。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="ac0b1-116">如果您使用的不是新的 Microsoft 365 系統管理中心，您可以選取位於首頁頂端的 \*\*[試用新的系統管理中心] \*\*開關將它開啟。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="ac0b1-117">在 [授權] 頁面上指派授權給使用者</span><span class="sxs-lookup"><span data-stu-id="ac0b1-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="ac0b1-118">您必須是全域系統管理員、計費系統管理員、授權系統管理員或使用者管理系統管理員。如需詳細資訊，請參閱[關於 Office 365 系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="ac0b1-119">使用 [授權]\*\*\*\* 頁面指派授權時，您可以指派特定產品的授權給最多 20 位使用者。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="ac0b1-120">在 [授權]\*\*\*\* 頁面上，您會看到您訂閱的所有產品清單，以及每個產品的授權總數、已獲指派多少個授權，以及有多少個授權可供使用。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="ac0b1-121">在系統管理中心中，前往 [帳單]\*\*\*\* > [授權][](https://go.microsoft.com/fwlink/p/?linkid=842264) 頁面。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![帳單視窗和功能表選項的螢幕擷取畫面。](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="ac0b1-123">選取您要指派授權的產品。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="ac0b1-124">Microsoft Teams 是免費版學生用 Office 365 A1 SKU 的一部分。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![[授權] 頁面的螢幕擷取畫面，其中包含可指派授權的產品。](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="ac0b1-126">選取 [指派授權]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-126">Select **Assign licenses**.</span></span>

   ![頁面的 [使用者] 區段的螢幕擷取畫面，[指派授權] 選項前面有加號。](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="ac0b1-128">在 [將授權指派給使用者]\*\*\*\* 窗格中，開始輸入名稱，這會產生名稱清單。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="ac0b1-129">從結果中選擇您要尋找的名稱，將它新增到清單中。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="ac0b1-130">一次最多可以新增 20 個使用者。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-130">You can add up to 20 users at a time.</span></span>

   ![[將授權指派給使用者] 頁面的螢幕擷取畫面，當中輸入了部分名稱，並顯示該部分名稱的搜尋結果。](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="ac0b1-132">選取 [開啟或關閉應用程式與服務]\*\*\*\* 以指派或移除特定項目 (例如 Microsoft Teams) 的存取權。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="ac0b1-133">請確認已選取 [Microsoft Teams]\*\*\*\* 和 [Office 網頁版 (教育)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="ac0b1-134">完成時，請選取 [指派]\*\*\*\*，然後選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="ac0b1-135">變更使用者可以存取的應用程式與服務：</span><span class="sxs-lookup"><span data-stu-id="ac0b1-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="ac0b1-136">選取包含使用者的列。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="ac0b1-137">在右窗格中，選取或取消選取您要授與存取權或移除存取權的應用程式與服務。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="ac0b1-138">完成時，請選取 [儲存]\*\*\*\*，然後選取 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="ac0b1-139">在 [作用中使用者] 頁面上將授權指派給個別或多個使用者</span><span class="sxs-lookup"><span data-stu-id="ac0b1-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="ac0b1-140">在系統管理中心中，移至 [使用者]\*\*\*\* > [[作用中使用者]](https://go.microsoft.com/fwlink/p/?linkid=834822) 頁面。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Microsoft O365 系統管理中心中 [作用中使用者] 功能表選項的螢幕擷取畫面。](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="ac0b1-142">選取您要指派授權的使用者名稱旁的圓圈。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![[作用中使用者] 頁面的螢幕擷取畫面，該頁面上作用中使用者清單中選取了部分使用者 (因為其名稱旁的圓圈是填滿的)。](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="ac0b1-144">在頂端選取 [管理產品授權]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-144">At the top select **Manage product licenses**.</span></span>

   ![[管理產品授權] 索引標籤的螢幕擷取畫面，下面有一位使用者列為 [未授權]。](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="ac0b1-146">在 [管理產品授權]\*\*\*\* 窗格中，選取 [新增到現有產品授權指派]\*\*\*\* > [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![[管理產品授權] 視窗的螢幕擷取畫面，其中已選取 [新增到現有產品授權指派] 選項按鈕。](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="ac0b1-148">在 [新增到現有產品]\*\*\*\* 窗格中，針對您已選取要指派授權的使用者，將開關切換到 [開啟]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="ac0b1-149">請確認已選取 [Microsoft Teams]\*\*\*\* 和 [Office 網頁版 (教育)]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![在 [新增到現有產品] 索引標籤上已選取 [Microsoft Teams] 和 [Office 網頁版 (教育)] 的螢幕擷取畫面。](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="ac0b1-151">根據預設，與這些授權相關的所有服務都會自動指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="ac0b1-152">您可以限制使用者能使用的服務。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="ac0b1-153">針對您不想讓使用者使用的服務，將開關切換至 [關閉]\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="ac0b1-154">在窗格底部，選取 [新增] > [關閉]。</span><span class="sxs-lookup"><span data-stu-id="ac0b1-154">At the bottom of the pane, select Add > Close.</span></span>
