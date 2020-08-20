---
title: Microsoft 團隊系統管理中心的團隊協力廠商應用程式購買服務
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: 瞭解如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上購買團隊協力廠商應用程式的服務。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: aeff6f363c1ae594a4a122055204d98b43d246e8
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818152"
---
<a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="805f5-103">Microsoft 團隊系統管理中心的團隊協力廠商應用程式購買服務</span><span class="sxs-lookup"><span data-stu-id="805f5-103">Purchase services for Teams third-party apps in the Microsoft Teams admin center</span></span>
======================================================

> [!NOTE]
> <span data-ttu-id="805f5-104">此功能目前僅適用于美國。</span><span class="sxs-lookup"><span data-stu-id="805f5-104">This feature is currently only available in the United States.</span></span>

<span data-ttu-id="805f5-105">團隊應用程式可以免費安裝，有些可能需要購買服務訂閱才能體驗 app 的完整功能與範圍。</span><span class="sxs-lookup"><span data-stu-id="805f5-105">Teams apps are free to install and some may require purchasing service subscriptions to experience the app's full functionality and scope.</span></span> <span data-ttu-id="805f5-106">這些服務訂閱稱為服務 (SaaS) 優惠，可透過 [AppSource](https://appsource.microsoft.com/) 購買，並透過 Microsoft 團隊系統管理中心立即購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-106">These service subscriptions are called Software as a Service (SaaS) offers, which are available for purchase through [AppSource](https://appsource.microsoft.com/) and now through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="805f5-107">Microsoft [團隊系統管理中心] 中的 [ [管理應用程式](manage-apps.md) ] 頁面是您可在其中查看及管理組織的所有團隊應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="805f5-107">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="805f5-108">例如，您可以查看應用程式的組織層級狀態和屬性、將新的自訂應用程式上傳到貴組織的 app 商店、封鎖或允許組織階層的應用程式，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="805f5-108">For example, you can see the org-level status and properties of apps, upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="805f5-109">您也可以在這裡，為貴組織中的使用者購買由協力廠商應用程式提供的服務授權。</span><span class="sxs-lookup"><span data-stu-id="805f5-109">Here, you can also purchase licenses for services offered by third-party apps for users in your organization.</span></span> <span data-ttu-id="805f5-110">資料表中的 [ **授權** ] 欄會指出 app 是否提供 SaaS 訂閱以進行購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-110">The **Licenses** column in the table indicates whether an app offers a SaaS subscription for purchase.</span></span>

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="顯示有 SaaS 訂閱之協力廠商 app 的螢幕擷取畫面":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a><span data-ttu-id="805f5-112">搜尋及購買協力廠商應用程式的服務</span><span class="sxs-lookup"><span data-stu-id="805f5-112">Search for and purchase services for a third-party app</span></span>

1. <span data-ttu-id="805f5-113">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="805f5-113">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="805f5-114">您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。</span><span class="sxs-lookup"><span data-stu-id="805f5-114">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="805f5-115">搜尋您要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="805f5-115">Search for the app that you want.</span></span> <span data-ttu-id="805f5-116">若要識別擁有付費 SaaS 訂閱的 app，請查看 [ **授權** ] 欄。</span><span class="sxs-lookup"><span data-stu-id="805f5-116">To identify apps that have a paid SaaS subscription, look in the **Licenses** column.</span></span> <span data-ttu-id="805f5-117">每個應用程式都將具有下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="805f5-117">Each app will have one of the following values:</span></span>
    - <span data-ttu-id="805f5-118">[**立即購買**]： App 提供 SaaS 訂閱，且可供購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-118">**Purchase now**: The app offers a SaaS subscription and is available to purchase.</span></span>  
    - <span data-ttu-id="805f5-119">已**購買**： App 提供 SaaS 訂閱，且您已為其購買授權。</span><span class="sxs-lookup"><span data-stu-id="805f5-119">**Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.</span></span>
    - <span data-ttu-id="805f5-120">**--**：應用程式不會提供 SaaS 訂閱。</span><span class="sxs-lookup"><span data-stu-id="805f5-120">**- -**: The app doesn't offer a SaaS subscription.</span></span>
3. <span data-ttu-id="805f5-121">找到應用程式後，請按一下 [ **立即購買** ]，移至 [應用程式詳細資料] 頁面的 [ **方案與定價** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="805f5-121">When you find the app, click **Purchase now** to go to the **Plans and pricing** tab of the app details page.</span></span> <span data-ttu-id="805f5-122">查看應用程式的 SaaS 優惠方案和價格資訊。</span><span class="sxs-lookup"><span data-stu-id="805f5-122">Review the plans and pricing information for the SaaS offer for the app.</span></span> <span data-ttu-id="805f5-123">如果您需要更多相關資訊，請按一下[AppSource](https://appsource.microsoft.com/)上的 [**深入瞭解**] 連結，移至應用程式的頁面。</span><span class="sxs-lookup"><span data-stu-id="805f5-123">If you need more information, click the **learn more** link to go to the app's page on [AppSource](https://appsource.microsoft.com/).</span></span>  
4. <span data-ttu-id="805f5-124">若要購買方案，請按一下 [ **立即購買**]。</span><span class="sxs-lookup"><span data-stu-id="805f5-124">To buy a plan, click **Purchase now**.</span></span> <span data-ttu-id="805f5-125">您將會被重新導向到與團隊 app 相關聯之優惠的購買體驗。</span><span class="sxs-lookup"><span data-stu-id="805f5-125">You'll be redirected to the purchase experience for the offer associated with the Teams app.</span></span> <span data-ttu-id="805f5-126">您可以在此完成服務或 SaaS 產品的購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-126">This is where you'll complete your purchase of the service or SaaS offer.</span></span>
5. <span data-ttu-id="805f5-127">選擇您想要的方案。</span><span class="sxs-lookup"><span data-stu-id="805f5-127">Choose the plan that you want.</span></span> <span data-ttu-id="805f5-128">如果 SaaS 提供包含一個以上的計畫，請按一下 [ **變更** ]，查看可用方案的清單。</span><span class="sxs-lookup"><span data-stu-id="805f5-128">If the SaaS offer includes more than one plan, click **Change** to see the list of available plans.</span></span>
6. <span data-ttu-id="805f5-129">選取您的帳單期限 ([ **每月** ] 或 [ **每年** ]) ，然後輸入您想要購買的使用者授權數目。</span><span class="sxs-lookup"><span data-stu-id="805f5-129">Select your billing term (either **Monthly** or **Yearly**), and then enter the number of user licenses that you want to buy.</span></span>
7. <span data-ttu-id="805f5-130">輸入您的付款條件。</span><span class="sxs-lookup"><span data-stu-id="805f5-130">Enter your payment method.</span></span>
8. <span data-ttu-id="805f5-131">當您準備好時，請選取 [ **下單**]。</span><span class="sxs-lookup"><span data-stu-id="805f5-131">When you're ready, select **Place order**.</span></span>
9. <span data-ttu-id="805f5-132">按一下 [ **立即設定** ]，在發行商的網站上啟動您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="805f5-132">Click **Configure now** to activate your subscription on the publisher's website.</span></span>

<span data-ttu-id="805f5-133">在您購買與團隊 app 相關聯的 SaaS 優惠之後，您可以在 [應用程式詳細資料] 頁面的 [ **方案與定價** ] 索引標籤上，查看下列購買詳細資料。</span><span class="sxs-lookup"><span data-stu-id="805f5-133">After you've purchased the SaaS offer associated with the Teams app, you can view the following purchase details on the **Plans and pricing** tab of the app details page.</span></span>

- <span data-ttu-id="805f5-134">**授權啟用日期**：啟用授權的日期。</span><span class="sxs-lookup"><span data-stu-id="805f5-134">**License activation date**: Date on which your license was activated.</span></span> <span data-ttu-id="805f5-135">如果您的帳戶尚未設定，這會顯示為 [ **訂閱擱置**中的啟用]。</span><span class="sxs-lookup"><span data-stu-id="805f5-135">If your account isn't yet set up, this shows as **Subscription pending activation**.</span></span>
- <span data-ttu-id="805f5-136">**授權**：您購買的授權數量。</span><span class="sxs-lookup"><span data-stu-id="805f5-136">**Licenses**: Number of licenses you purchased.</span></span>

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="[應用程式詳細資料] 頁面的 [方案與定價] 索引標籤":::

<span data-ttu-id="805f5-138">選取 [ **管理授權** ]，移至 Microsoft 365 系統管理中心，以查看及管理您購買的授權，並管理使用者的授權指派。</span><span class="sxs-lookup"><span data-stu-id="805f5-138">Select **Manage licenses** to go to the Microsoft 365 admin center to view and manage the licenses you purchased and to manage license assignments for users.</span></span>

<span data-ttu-id="805f5-139">全域管理員可以查看組織中任何人所進行的購買，而團隊服務管理員只能查看自己所進行的購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-139">Global admins can view the purchases made by anyone in the organization whereas Teams service admins can only view the purchases made by themselves.</span></span>  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a><span data-ttu-id="805f5-140">您想要在 Microsoft 團隊系統管理中心及 AppSource 中列出並銷售的小組 app 提供 SaaS 優惠嗎？</span><span class="sxs-lookup"><span data-stu-id="805f5-140">Have a SaaS offer for a Teams app that you want to list and sell in the Microsoft Teams admin center and AppSource?</span></span>

<span data-ttu-id="805f5-141">開發人員可以建立與其小組 app 相關聯的 SaaS 產品。</span><span class="sxs-lookup"><span data-stu-id="805f5-141">Developers can create SaaS offers associated with their Teams apps.</span></span> <span data-ttu-id="805f5-142">這些優惠是透過 [合作夥伴中心](https://partner.microsoft.com) 發佈，且可供組織透過 [AppSource](https://appsource.microsoft.com/) 和 Microsoft 團隊系統管理中心購買。</span><span class="sxs-lookup"><span data-stu-id="805f5-142">These offers are published through [Partner Center](https://partner.microsoft.com) and are available for organizations to purchase through [AppSource](https://appsource.microsoft.com/) and the Microsoft Teams admin center.</span></span>
 
<span data-ttu-id="805f5-143">協力廠商應用程式開發人員可以移至 [建立 SaaS 優惠](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) ，以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="805f5-143">Third-party app developers can go to [Create a SaaS offer](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) for more information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="805f5-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="805f5-144">Related topics</span></span>

- [<span data-ttu-id="805f5-145">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="805f5-145">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="805f5-146">建立 SaaS 優惠</span><span class="sxs-lookup"><span data-stu-id="805f5-146">Create a SaaS offer</span></span>](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
