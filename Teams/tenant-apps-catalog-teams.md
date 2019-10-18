---
title: 在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 在 Microsoft 團隊租使用者應用程式目錄中發佈 app 的指導方針。
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5affe464ac300d0084916ad8ec0044ca74f8fa6b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570077"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="687f5-103">在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式</span><span class="sxs-lookup"><span data-stu-id="687f5-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="687f5-104">您可以使用 Microsoft 團隊租使用者應用程式目錄來測試和發佈業務線應用程式至您的組織。</span><span class="sxs-lookup"><span data-stu-id="687f5-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="687f5-105">[團隊租使用者應用程式目錄] 可讓您散佈專為您的組織建立且您依賴來完成重要業務功能的業務線應用程式。</span><span class="sxs-lookup"><span data-stu-id="687f5-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="687f5-106">若要為您的組織發佈應用程式，請使用具有全域管理員或團隊服務管理員角色的帳戶登入您的小組用戶端，然後依照下列指示進行。</span><span class="sxs-lookup"><span data-stu-id="687f5-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="687f5-107">在來自團隊用戶端的租使用者應用程式目錄中發佈應用程式</span><span class="sxs-lookup"><span data-stu-id="687f5-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="687f5-108">您必須使用已啟用全域管理員或團隊服務管理員角色的帳戶登入 Microsoft 團隊用戶端，才能為您的組織發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="687f5-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="687f5-109">深入瞭解如何[使用系統管理員角色來管理團隊](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="687f5-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="687f5-110">取得團隊應用程式套件</span><span class="sxs-lookup"><span data-stu-id="687f5-110">Get a Teams app package</span></span>

<span data-ttu-id="687f5-111">團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。</span><span class="sxs-lookup"><span data-stu-id="687f5-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="687f5-112">有了應用程式套件之後，您就可以將它新增至企業應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="687f5-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="687f5-113">雖然租使用者中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務系統管理員具備發佈及管理的功能。</span><span class="sxs-lookup"><span data-stu-id="687f5-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="687f5-114">移至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="687f5-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="687f5-115">啟動 Microsoft 團隊用戶端，然後使用您的全域或團隊服務管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="687f5-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="687f5-116">從 [Microsoft 團隊] 商店中，選取名為 [您的特定組織] （在此範例中為 [Contoso]）的新節。</span><span class="sxs-lookup"><span data-stu-id="687f5-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="687f5-117">貴組織中的使用者可以在目錄中查看應用程式，並為他們所屬的小組安裝這些 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="687f5-119">將應用程式新增至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="687f5-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="687f5-120">從商店中，選取 **[上傳 Contoso 的自訂應用程式** > **上傳**]。</span><span class="sxs-lookup"><span data-stu-id="687f5-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="687f5-122">（您也可以選擇 [**上傳給我] 或 [我的小組**]，這稱為 [側*載*]。</span><span class="sxs-lookup"><span data-stu-id="687f5-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="687f5-123">[邊載] 可讓您的小組或您選取的小組使用該 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="687f5-124">流覽至該應用程式套件，選取它，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="687f5-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image03.png)

<span data-ttu-id="687f5-126">當您回到您的租使用者應用程式目錄時，新的企業 app 就會出現在該處。</span><span class="sxs-lookup"><span data-stu-id="687f5-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="687f5-127">請記住，只有您和貴組織的成員才能存取此應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="687f5-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="687f5-128">更新租使用者應用程式目錄中的應用程式</span><span class="sxs-lookup"><span data-stu-id="687f5-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="687f5-129">從您的租使用者應用程式目錄中，選取 "**...**"</span><span class="sxs-lookup"><span data-stu-id="687f5-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="687f5-130">在您要更新的應用程式右上方。</span><span class="sxs-lookup"><span data-stu-id="687f5-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="687f5-131">流覽至已更新的應用程式套件，選取它，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="687f5-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image04.png)

<span data-ttu-id="687f5-133">App 將會修正為版本2.0。</span><span class="sxs-lookup"><span data-stu-id="687f5-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="687f5-134">您也可以從這個功能表刪除整個公司的 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="687f5-135">使用 Office 365 管理入口網站管理租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="687f5-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="687f5-136">如果您有需要修正錯誤的 app，您可以透過 Office 365 系統管理入口網站暫時停用 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="687f5-137">選取 [**設定** > **服務] & 的增益集** > **Microsoft 團隊**。</span><span class="sxs-lookup"><span data-stu-id="687f5-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="687f5-138">除了先前的設定之外，現在還有一個章節專門用於貴公司的 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="687f5-139">您可以選擇要啟用或停用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="687f5-139">You can choose which apps you want to enable or disable.</span></span>

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image05.png)

<span data-ttu-id="687f5-141">停用應用程式將會封鎖使用者與 app 的互動，而不需要徹底刪除 app。</span><span class="sxs-lookup"><span data-stu-id="687f5-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="687f5-142">當您在企業中管理 app 時，這些控制項可提供額外的靈活性和控制權。</span><span class="sxs-lookup"><span data-stu-id="687f5-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
