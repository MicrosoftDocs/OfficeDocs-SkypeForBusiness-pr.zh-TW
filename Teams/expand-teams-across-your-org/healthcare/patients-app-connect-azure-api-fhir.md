---
title: 將病患應用程式連線至 Azure API for FHIR
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何將 Microsoft 團隊中的患者 app 連線至 Azure API，以 FHIR (快速醫療保健互通性資源) 。
ms.openlocfilehash: cf59b7bddbd1a480a2e1a2f7d9381f3fdf59d210
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277303"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="b62d4-103">將病患應用程式連線至 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="b62d4-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b62d4-104">**2020年9月30日生效，患者 app 將會被否決，且使用者將無法從 [小組] app store 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="b62d4-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="b62d4-105">患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。</span><span class="sxs-lookup"><span data-stu-id="b62d4-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="b62d4-106">當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。</span><span class="sxs-lookup"><span data-stu-id="b62d4-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="b62d4-107">目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。</span><span class="sxs-lookup"><span data-stu-id="b62d4-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="b62d4-108">[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b62d4-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="b62d4-109">透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。</span><span class="sxs-lookup"><span data-stu-id="b62d4-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="b62d4-110">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="b62d4-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="b62d4-111">請依照下列步驟，允許 Microsoft 團隊中的患者 app 存取 FHIR 實例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="b62d4-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="b62d4-112">本文假設您有在您的租使用者中設定和設定 [FHIR 實例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。</span><span class="sxs-lookup"><span data-stu-id="b62d4-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="b62d4-113">如果您還沒有在租使用者中建立 FHIR 實例的 Azure API，請參閱 [快速入門：使用 azure 入口網站部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="b62d4-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="b62d4-114">按一下 [這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 以授與系統管理員同意的患者 app。</span><span class="sxs-lookup"><span data-stu-id="b62d4-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="b62d4-115">出現提示時，請使用您的租使用者管理員或全域系統管理員認證登入，然後按一下 [ **接受** ] 以授與所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b62d4-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="b62d4-117">接受之後，請關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="b62d4-117">After you accept, close the window.</span></span> <span data-ttu-id="b62d4-118">您會看到一個頁面，看起來會像這樣。</span><span class="sxs-lookup"><span data-stu-id="b62d4-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="b62d4-119">您可以忽略頁面上的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b62d4-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="b62d4-120">這不是無害的，指出已授與同意。</span><span class="sxs-lookup"><span data-stu-id="b62d4-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="b62d4-121"> (我們正在處理更適合此 URL 的方便使用頁面。</span><span class="sxs-lookup"><span data-stu-id="b62d4-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="b62d4-122">掌握最新資訊！ ) </span><span class="sxs-lookup"><span data-stu-id="b62d4-122">Stay tuned!)</span></span>

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="b62d4-124">使用您的系統管理員認證登入 [Azure 入口網站](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="b62d4-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="b62d4-125">在左側導覽中，選取 [ **Azure Active Directory**]，然後選取 [ **企業應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b62d4-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="b62d4-126">尋找名為 [ \*\*患者 (dev) \*\*的列，然後將 [ **物件識別碼** ] 欄中的值複製到 [剪貼簿]。</span><span class="sxs-lookup"><span data-stu-id="b62d4-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="b62d4-127">![Azure 入口網站) 資料列的患者 (開發人員的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="b62d4-127">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="b62d4-128">若要將患者 (app 連線至 FHIR 資源實例的 Azure API，請進行搜尋，或流覽您的資源) ，然後開啟該實例的設定。</span><span class="sxs-lookup"><span data-stu-id="b62d4-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure API for Azure 入口網站中的 FHIR 實例設定的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="b62d4-130">按一下 [ **驗證**]，然後將您在步驟3中複製的物件識別碼貼到 [ **允許的物件識別碼** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="b62d4-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="b62d4-131">這可讓患者 app 存取 FHIR 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b62d4-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="b62d4-132">貼上物件識別碼之後，Azure Active Directory 會進行驗證，且旁邊會出現一個綠色的核取記號。</span><span class="sxs-lookup"><span data-stu-id="b62d4-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 入口網站驗證設定的螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="b62d4-134">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b62d4-134">Click **Save**.</span></span> <span data-ttu-id="b62d4-135">這會 redeploys 實例，可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="b62d4-135">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="b62d4-136">按一下 **[概述**]，然後從 **FHIR 中繼資料端點**複製 URL。</span><span class="sxs-lookup"><span data-stu-id="b62d4-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="b62d4-137">移除元資料標記以取得 FHIR 伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="b62d4-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="b62d4-138">例如， https://test02-teamshealth.azurehealthcareapis.com/ 。</span><span class="sxs-lookup"><span data-stu-id="b62d4-138">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 入口網站中中繼資料端點的螢幕擷取畫面](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="b62d4-140">在 [團隊] 中，移至您團隊中載入的患者應用程式實例，按一下 [ **設定**]，然後在 [ **連結** ] 方塊中輸入 FHIR 伺服器端點 URL。</span><span class="sxs-lookup"><span data-stu-id="b62d4-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="b62d4-141">接著，按一下 **[連線]** 以建立連線並搜尋，並將患者新增至您的清單。</span><span class="sxs-lookup"><span data-stu-id="b62d4-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![團隊中的患者 app 設定的螢幕擷取畫面](../../media/patients-app-teams.png)
    
    <span data-ttu-id="b62d4-143">如果您在執行此步驟時，在連線至團隊時收到錯誤，請傳送錯誤的詳細螢幕擷取畫面、 [Fiddler](https://www.telerik.com/download/fiddler) 的記錄，以及電子郵件中包含「患者 APP – EMR 模式疑難排解」主題行的任何其他重現步驟，以進行 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b62d4-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b62d4-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="b62d4-144">Related topics</span></span>

- [<span data-ttu-id="b62d4-145">病患應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="b62d4-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="b62d4-146">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b62d4-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
