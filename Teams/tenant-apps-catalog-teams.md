---
title: 在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: 在 Microsoft 團隊租使用者應用程式目錄中發佈 app 的指導方針。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161612"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="7a068-103">在 Microsoft 團隊租使用者應用程式目錄中發佈應用程式</span><span class="sxs-lookup"><span data-stu-id="7a068-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="7a068-104">您可以使用 Microsoft 團隊租使用者應用程式目錄來測試和發佈業務線應用程式至您的組織。</span><span class="sxs-lookup"><span data-stu-id="7a068-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="7a068-105">[團隊租使用者] 應用程式目錄可讓您散佈專為您的組織建立且您依賴來完成重要業務功能的業務線應用程式。</span><span class="sxs-lookup"><span data-stu-id="7a068-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="7a068-106">若要為您的組織發佈應用程式，請使用具有全域管理員或團隊服務管理員角色的帳戶登入團隊用戶端，然後遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7a068-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="7a068-107">在來自團隊用戶端的租使用者應用程式目錄中發佈應用程式</span><span class="sxs-lookup"><span data-stu-id="7a068-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="7a068-108">這些步驟說明如何使用 [團隊用戶端] 發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="7a068-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="7a068-109">您也可以在 Microsoft 團隊系統管理中心的 [**管理應用程式**] 頁面上發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="7a068-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7a068-110">若要深入瞭解，請參閱[管理團隊中的應用程式](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="7a068-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="7a068-111">取得團隊應用程式套件</span><span class="sxs-lookup"><span data-stu-id="7a068-111">Get a Teams app package</span></span>

<span data-ttu-id="7a068-112">團隊應用程式套件是使用[團隊 App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)建立的。</span><span class="sxs-lookup"><span data-stu-id="7a068-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="7a068-113">有了應用程式套件之後，您就可以將它新增到租使用者應用程式目錄中。</span><span class="sxs-lookup"><span data-stu-id="7a068-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="7a068-114">雖然貴組織中的所有使用者都可以查看應用程式目錄，但只有全域管理員和團隊服務管理員具備發佈及管理該功能的能力。</span><span class="sxs-lookup"><span data-stu-id="7a068-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="7a068-115">移至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="7a068-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="7a068-116">啟動團隊並使用您的全域或團隊服務管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="7a068-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="7a068-117">選取應用程式左側的 [**應用程式**]，然後選取名為 [您的特定組織] （在此範例中為 Contoso）的新節。</span><span class="sxs-lookup"><span data-stu-id="7a068-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="7a068-118">貴組織中的使用者可以在目錄中查看應用程式，並為他們所屬的小組安裝這些 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="7a068-120">將應用程式新增至租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="7a068-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="7a068-121">在 [**應用程式**] 頁面上，選取 **[上傳 Contoso 的自訂應用程式** > 上**傳**]。</span><span class="sxs-lookup"><span data-stu-id="7a068-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image02.png)

    <span data-ttu-id="7a068-123">（您也可以選擇 [**上傳給我] 或 [我的小組**]，這稱為 [側*載*]。</span><span class="sxs-lookup"><span data-stu-id="7a068-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="7a068-124">[邊載] 可讓您的小組或您選取的小組使用該 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="7a068-125">流覽至該應用程式套件，選取它，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7a068-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image03.png)

<span data-ttu-id="7a068-127">當您回到您的租使用者應用程式目錄時，新的企業 app 就會出現在該處。</span><span class="sxs-lookup"><span data-stu-id="7a068-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="7a068-128">請記住，只有您和貴組織的成員才能存取此應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="7a068-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="7a068-129">在租使用者應用程式目錄中更新應用程式</span><span class="sxs-lookup"><span data-stu-id="7a068-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="7a068-130">從您的租使用者應用程式目錄中，選取 "**...**"</span><span class="sxs-lookup"><span data-stu-id="7a068-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="7a068-131">在您要更新的應用程式右上方。</span><span class="sxs-lookup"><span data-stu-id="7a068-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="7a068-132">流覽至已更新的應用程式套件，選取它，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="7a068-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![顯示 [應用程式目錄] 的 [小組] App 存放區的螢幕擷取畫面。](media/private-app-store-teams-image04.png)

<span data-ttu-id="7a068-134">App 將會修正為版本2.0。</span><span class="sxs-lookup"><span data-stu-id="7a068-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="7a068-135">您也可以從這個功能表刪除整個公司的 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="7a068-136">使用 Microsoft 團隊系統管理中心來管理租使用者應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="7a068-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="7a068-137">如果您的應用程式需要修正錯誤，您可以暫時停用應用程式許可權原則中的使用者 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="7a068-138">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="7a068-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="7a068-139">選取您要編輯的 app 許可權原則，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7a068-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="7a068-140">在 [**租使用者應用程式**] 底下，選取 [**封鎖特定的 app 並允許所有其他 app**]，然後新增您想要封鎖的 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="7a068-141">停用 app 會封鎖使用者與 app 的互動，而不需要徹底刪除 app。</span><span class="sxs-lookup"><span data-stu-id="7a068-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="7a068-142">當您管理組織中的 app 時，這些控制項可提供額外的靈活性與控制權。</span><span class="sxs-lookup"><span data-stu-id="7a068-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="7a068-143">若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7a068-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>