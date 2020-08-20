---
title: 在 Microsoft 團隊系統管理中心中查看應用程式許可權並授與系統管理員同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何查看 app 要求的許可權，以及如何在 Microsoft 團隊系統管理中心的 [管理應用程式] 頁面上，授與系統管理員的同意。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814607"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="527af-103">在 Microsoft 團隊系統管理中心中查看應用程式許可權並授與系統管理員同意</span><span class="sxs-lookup"><span data-stu-id="527af-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="527af-104">Microsoft [團隊系統管理中心] 中的 [ [管理應用程式](manage-apps.md) ] 頁面是您可在其中查看及管理組織的所有團隊應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="527af-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="527af-105">例如，您可以查看應用程式的組織層級狀態和屬性、核准或上傳新的自訂應用程式至組織的 app 商店、封鎖或允許組織階層的應用程式，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="527af-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="527af-106">您也可以在這裡，授與組織範圍的系統管理員同意要求存取資料許可權的 app，以及查看資源特定的同意 (RSC) 應用程式的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="527af-107">授與整個組織的系統管理員同意應用程式</span><span class="sxs-lookup"><span data-stu-id="527af-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="527af-108">做為管理員，您可以查看並同意代表貴組織中所有使用者要求許可權的 app。</span><span class="sxs-lookup"><span data-stu-id="527af-108">As an admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="527af-109">您這樣做是為了讓使用者在啟動 app 時，不需要查看並接受 app 要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="527af-110">此外，根據 Azure Active Directory (Azure AD) 中使用者的 [同意設定](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) 而定，部分使用者可能不允許取得存取公司資料之 app 的授權。</span><span class="sxs-lookup"><span data-stu-id="527af-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="527af-111">應用程式要求的許可權範例包括讀取儲存在小組中的資訊、讀取使用者的設定檔，以及代表使用者傳送電子郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="527af-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="527af-112">若要深入瞭解，請參閱 [Microsoft 身分識別平臺端點中的許可權和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="527af-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="527af-113">您必須是全域系統管理員，才能向 app 授與整個組織的同意。</span><span class="sxs-lookup"><span data-stu-id="527af-113">You have to be a global admin to grant org-wide consent to an app.</span></span> <span data-ttu-id="527af-114">[ **許可權** ] 欄會指出 app 是否擁有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-114">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="527af-115">您會看到在 Azure AD 中註冊的每個應用程式的 [ **查看詳細資料** ] 連結，該 app 具有需要同意的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-115">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="527af-116">請記住，這只適用于自訂和協力廠商應用程式和。</span><span class="sxs-lookup"><span data-stu-id="527af-116">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="527af-117">您不會看到此連結，或需要為 Microsoft 發佈的 app 授與系統管理員的同意。</span><span class="sxs-lookup"><span data-stu-id="527af-117">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[管理應用程式] 頁面上 [許可權] 欄的螢幕擷取畫面":::

<span data-ttu-id="527af-119">若要向 app 授與整個組織的同意，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="527af-119">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="527af-120">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="527af-120">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="527af-121">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="527af-121">Do one of the following:</span></span>
    - <span data-ttu-id="527af-122">搜尋您要的應用程式，按一下應用程式名稱以移至 [應用程式詳細資料] 頁面，然後選取 [ **許可權** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="527af-122">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="527af-123">以遞減順序排序 [ **許可權** ] 欄，以尋找應用程式，然後選取 [ **查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="527af-123">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="527af-124">這麼做會將您帶到 [應用程式詳細資料] 頁面的 [ **許可權** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="527af-124">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="527af-125">在 [ **全組織許可權**] 底下，選取 [ **審查許可權和同意**]。</span><span class="sxs-lookup"><span data-stu-id="527af-125">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span> <span data-ttu-id="527af-126">您必須是全域系統管理員才能執行此動作。</span><span class="sxs-lookup"><span data-stu-id="527af-126">You must be a global admin to do this.</span></span> <span data-ttu-id="527af-127">[團隊服務管理員] 無法使用此選項。</span><span class="sxs-lookup"><span data-stu-id="527af-127">This option isn't available to Teams service admins.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="App 之 [許可權] 索引標籤上組織範圍許可權的螢幕擷取畫面":::

4. <span data-ttu-id="527af-129">在 [ **許可權** ] 索引標籤上，查看 app 所要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-129">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="應用程式所要求之許可權的螢幕擷取畫面":::

    > [!IMPORTANT]
    > <span data-ttu-id="527af-131">向 app 授與整個組織的同意，就能讓 app 存取貴組織的資料。</span><span class="sxs-lookup"><span data-stu-id="527af-131">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="527af-132">在准許同意前，請仔細檢查 app 要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-132">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="527af-133">如果您同意 app 要求的許可權，請按一下 [ **接受** ] 以授與同意。</span><span class="sxs-lookup"><span data-stu-id="527af-133">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="527af-134">橫幅會暫時出現在頁面頂端，讓您知道該 app 已授與要求的許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-134">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="527af-135">App 現在可以存取貴組織中所有使用者的指定資源，且不會提示其他人查看許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-135">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="527af-136">在您接受許可權之後，您會在 [應用程式詳細資料] 頁面上的 [ **全組織許可權** ] 下看到一則訊息，告知您已獲「同意」。</span><span class="sxs-lookup"><span data-stu-id="527af-136">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="527af-137">若要查看應用程式許可權的詳細資料，請按一下 **Azure Active Directory** 連結，移至 Azure AD 入口網站中的 app 頁面。</span><span class="sxs-lookup"><span data-stu-id="527af-137">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="授與同意時所顯示之訊息的螢幕擷取畫面":::

<span data-ttu-id="527af-139">如果您組織中的使用者可以授與同意，且如果一或多位使用者獲准同意某個特定的 app，您就只會看到訊息，告訴您同意已授與 Azure Active Directory 連結。</span><span class="sxs-lookup"><span data-stu-id="527af-139">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll only see the message to let you know that consent was granted and the Azure Active Directory link.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="527af-140">查看應用程式的資源特定同意許可權</span><span class="sxs-lookup"><span data-stu-id="527af-140">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="527af-141">RSC 許可權讓小組擁有者同意 app 存取及修改小組資料的授權。</span><span class="sxs-lookup"><span data-stu-id="527af-141">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="527af-142">RSC 許可權是精確、團隊特有的許可權，可定義應用程式在特定團隊中的功能。</span><span class="sxs-lookup"><span data-stu-id="527af-142">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="527af-143">RSC 許可權的範例包括建立及刪除頻道、取得團隊設定，以及建立及移除頻道索引標籤的功能。</span><span class="sxs-lookup"><span data-stu-id="527af-143">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> <span data-ttu-id="527af-144">RSC 許可權是在應用程式資訊清單中定義，而不是在 Azure AD 中定義。</span><span class="sxs-lookup"><span data-stu-id="527af-144">RSC permissions are defined in the app manifest and not in Azure AD.</span></span>

<span data-ttu-id="527af-145">當您將應用程式新增至團隊時，您同意對 RSC 許可權的授權。</span><span class="sxs-lookup"><span data-stu-id="527af-145">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="527af-146">若要深入瞭解，請參閱小組中 (RSC) 與[資源特定同意的](resource-specific-consent.md)[資源特定同意](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。</span><span class="sxs-lookup"><span data-stu-id="527af-146">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) and [Resource-specific consent in Teams](resource-specific-consent.md).</span></span>

<span data-ttu-id="527af-147">全域管理員和團隊服務系統管理員可以查看 RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-147">Global admins and Teams service admin can view RSC permissions.</span></span> <span data-ttu-id="527af-148">若要查看應用程式的 RSC 許可權，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="527af-148">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="527af-149">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="527af-149">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="527af-150">搜尋您要的應用程式，按一下應用程式名稱以移至 [應用程式詳細資料] 頁面，然後選取 [ **許可權** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="527af-150">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="527af-151">在 [ **Microsoft Graph 資源特定同意 (RSC) 許可權]** 下，查看 app 要求的 RSC 許可權。</span><span class="sxs-lookup"><span data-stu-id="527af-151">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="應用程式的 RSC 許可權的螢幕擷取畫面":::

## <a name="related-topics"></a><span data-ttu-id="527af-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="527af-153">Related topics</span></span>

- [<span data-ttu-id="527af-154">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="527af-154">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="527af-155">Microsoft 身分識別平臺端點的許可權和同意</span><span class="sxs-lookup"><span data-stu-id="527af-155">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="527af-156">小組中的資源特定同意</span><span class="sxs-lookup"><span data-stu-id="527af-156">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="527af-157"> (RSC) 的資源特定同意 </span><span class="sxs-lookup"><span data-stu-id="527af-157">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


