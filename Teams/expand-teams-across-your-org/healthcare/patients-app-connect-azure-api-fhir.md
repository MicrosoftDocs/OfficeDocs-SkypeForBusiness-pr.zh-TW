---
title: 將病患應用程式連線至 Azure API for FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 瞭解如何將 Microsoft Teams 中的病患應用程式連接到適用于 FHIR 的 Azure API， (快速醫療保健互通性資源) 。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096265"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="672cf-103">將病患應用程式連線至 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="672cf-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="672cf-104">自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。</span><span class="sxs-lookup"><span data-stu-id="672cf-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="672cf-105">病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="672cf-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="672cf-106">所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="672cf-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="672cf-107">使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。</span><span class="sxs-lookup"><span data-stu-id="672cf-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="672cf-108">使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。</span><span class="sxs-lookup"><span data-stu-id="672cf-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="672cf-109">請查看清單中的病患範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="672cf-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="672cf-110">若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="672cf-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="672cf-111">請遵循下列步驟，允許 Microsoft Teams 中的病患應用程式存取 FHIR 實例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="672cf-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="672cf-112">本文假設您在租使用者中設定並設定 [了 FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 實例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="672cf-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="672cf-113">如果您尚未在租使用者中建立 FHIR 實例的 Azure API，請參閱快速入門：使用 Azure 入口網站部署[FHIR 的 Azure API。](/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="672cf-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="672cf-114">按一下 [這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 以授予病患應用程式的系統管理員同意。</span><span class="sxs-lookup"><span data-stu-id="672cf-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="672cf-115">當系統提示時，使用租使用者系統管理員或全域系統管理員認證來登錄，然後按一下 **[接受** 以授予必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="672cf-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![病患應用程式的許可權要求螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="672cf-117">接受之後，請關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="672cf-117">After you accept, close the window.</span></span> <span data-ttu-id="672cf-118">您會看到看起來像這樣的頁面。</span><span class="sxs-lookup"><span data-stu-id="672cf-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="672cf-119">您可以忽略頁面上的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="672cf-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="672cf-120">這是無害的，且表示已同意。</span><span class="sxs-lookup"><span data-stu-id="672cf-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="672cf-121"> (我們正在為此 URL 建立一個更為使用者方便的頁面。</span><span class="sxs-lookup"><span data-stu-id="672cf-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="672cf-122">請留意！) </span><span class="sxs-lookup"><span data-stu-id="672cf-122">Stay tuned!)</span></span>

    ![病患應用程式的許可權要求螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="672cf-124">使用系統管理員 [認證](https://portal.azure.com) 來登錄 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="672cf-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="672cf-125">在左側流覽中，選取 **Azure Active Directory，** 然後選取 **企業應用程式**。</span><span class="sxs-lookup"><span data-stu-id="672cf-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="672cf-126">尋找名為 **Patients** (dev) 列，然後將物件 **識別碼** 欄中的值複製到剪貼簿。</span><span class="sxs-lookup"><span data-stu-id="672cf-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Azure 入口網站中 (病患) 列的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="672cf-128">請前往您想要將病患應用程式連接到的 FHIR 資源實例的 Azure API (搜尋或流覽您的資源) ，然後開啟該實例的設定。</span><span class="sxs-lookup"><span data-stu-id="672cf-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure 入口網站 FHIR 實例設定 Azure API 的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="672cf-130">按一下 **[驗證**，然後貼上您于步驟 3 中複製的物件識別碼至 [ **允許的物件識別碼>** 方塊。</span><span class="sxs-lookup"><span data-stu-id="672cf-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="672cf-131">這可讓病患應用程式存取 FHIR 伺服器。</span><span class="sxs-lookup"><span data-stu-id="672cf-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="672cf-132">貼上物件識別碼之後，Azure Active Directory 會驗證它，其旁邊會出現綠色核取方塊。</span><span class="sxs-lookup"><span data-stu-id="672cf-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 入口網站驗證設定螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="672cf-134">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="672cf-134">Click **Save**.</span></span> <span data-ttu-id="672cf-135">這會重新部署實例，可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="672cf-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="672cf-136">按一下 **[概** 觀，然後從 **FHIR 中繼資料端點複製 URL。**</span><span class="sxs-lookup"><span data-stu-id="672cf-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="672cf-137">移除元資料標記以取得 FHIR 伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="672cf-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="672cf-138">例如 `https://test02-teamshealth.azurehealthcareapis.com/` ，。</span><span class="sxs-lookup"><span data-stu-id="672cf-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Azure 入口網站中的中繼資料端點](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="672cf-140">在 Teams 中，前往小組中載入的病患應用程式實例，按一下 [設定>，然後在 [連結> 方塊中，輸入 FHIR 伺服器端點 URL。</span><span class="sxs-lookup"><span data-stu-id="672cf-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="672cf-141">接著，按一下 **[連接** 以建立連接並搜尋病患並新增到您的清單。</span><span class="sxs-lookup"><span data-stu-id="672cf-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="672cf-142">Teams 中的病患應用程式設定</span><span class="sxs-lookup"><span data-stu-id="672cf-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="672cf-143">如果您在此步驟期間連接到 Teams 時發生錯誤，請傳送錯誤的詳細螢幕擷取畫面、[來自 Fiddler](https://www.telerik.com/download/fiddler)的記錄，以及電子郵件中任何其他回復步驟，其主題行為 「病患 App – EMR 模式疑難排解[」到 teamsforhealthcare@service.microsoft.com。](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="672cf-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="672cf-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="672cf-144">Related topics</span></span>

- [<span data-ttu-id="672cf-145">病患應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="672cf-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="672cf-146">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="672cf-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)