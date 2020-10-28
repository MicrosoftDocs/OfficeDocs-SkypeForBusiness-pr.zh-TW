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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e3ff2f42953d59d1eecbc96179759f2ad9024f82
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772254"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="172bf-103">將病患應用程式連線至 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="172bf-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="172bf-104">2020年10月30日生效，患者 app 已停用，且已由小組中的 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。</span><span class="sxs-lookup"><span data-stu-id="172bf-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="172bf-105">透過清單，您的醫療保健組織中的 [護理小組] 可建立案例的患者清單，包括從倒圓角和 interdisciplinary 小組會議到一般患者監視。</span><span class="sxs-lookup"><span data-stu-id="172bf-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="172bf-106">查看清單中的患者範本以開始使用。</span><span class="sxs-lookup"><span data-stu-id="172bf-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="172bf-107">若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="172bf-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="172bf-108">請依照下列步驟，允許 Microsoft 團隊中的患者 app 存取 FHIR 實例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="172bf-108">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="172bf-109">本文假設您有在您的租使用者中設定和設定 [FHIR 實例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。</span><span class="sxs-lookup"><span data-stu-id="172bf-109">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="172bf-110">如果您還沒有在租使用者中建立 FHIR 實例的 Azure API，請參閱 [快速入門：使用 azure 入口網站部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="172bf-110">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="172bf-111">按一下 [這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 以授與系統管理員同意的患者 app。</span><span class="sxs-lookup"><span data-stu-id="172bf-111">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="172bf-112">出現提示時，請使用您的租使用者管理員或全域系統管理員認證登入，然後按一下 [ **接受** ] 以授與所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="172bf-112">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="172bf-114">接受之後，請關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="172bf-114">After you accept, close the window.</span></span> <span data-ttu-id="172bf-115">您會看到一個頁面，看起來會像這樣。</span><span class="sxs-lookup"><span data-stu-id="172bf-115">You'll see a page that may look like this.</span></span> <span data-ttu-id="172bf-116">您可以忽略頁面上的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="172bf-116">You can ignore the error message on the page.</span></span> <span data-ttu-id="172bf-117">這不是無害的，指出已授與同意。</span><span class="sxs-lookup"><span data-stu-id="172bf-117">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="172bf-118"> (我們正在處理更適合此 URL 的方便使用頁面。</span><span class="sxs-lookup"><span data-stu-id="172bf-118">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="172bf-119">掌握最新資訊！ ) </span><span class="sxs-lookup"><span data-stu-id="172bf-119">Stay tuned!)</span></span>

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="172bf-121">使用您的系統管理員認證登入 [Azure 入口網站](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="172bf-121">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="172bf-122">在左側導覽中，選取 [ **Azure Active Directory** ]，然後選取 [ **企業應用程式** ]。</span><span class="sxs-lookup"><span data-stu-id="172bf-122">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="172bf-123">尋找名為 [ **患者 (dev)** 的列，然後將 [ **物件識別碼** ] 欄中的值複製到 [剪貼簿]。</span><span class="sxs-lookup"><span data-stu-id="172bf-123">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Azure 入口網站) 資料列的患者 (開發人員的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="172bf-125">若要將患者 (app 連線至 FHIR 資源實例的 Azure API，請進行搜尋，或流覽您的資源) ，然後開啟該實例的設定。</span><span class="sxs-lookup"><span data-stu-id="172bf-125">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure API for Azure 入口網站中的 FHIR 實例設定的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="172bf-127">按一下 [ **驗證** ]，然後將您在步驟3中複製的物件識別碼貼到 [ **允許的物件識別碼** ] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="172bf-127">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="172bf-128">這可讓患者 app 存取 FHIR 伺服器。</span><span class="sxs-lookup"><span data-stu-id="172bf-128">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="172bf-129">貼上物件識別碼之後，Azure Active Directory 會進行驗證，且旁邊會出現一個綠色的核取記號。</span><span class="sxs-lookup"><span data-stu-id="172bf-129">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 入口網站驗證設定的螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="172bf-131">按一下 [儲存]  。</span><span class="sxs-lookup"><span data-stu-id="172bf-131">Click **Save** .</span></span> <span data-ttu-id="172bf-132">這會 redeploys 實例，可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="172bf-132">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="172bf-133">按一下 **[概述** ]，然後從 **FHIR 中繼資料端點** 複製 URL。</span><span class="sxs-lookup"><span data-stu-id="172bf-133">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="172bf-134">移除元資料標記以取得 FHIR 伺服器 URL。</span><span class="sxs-lookup"><span data-stu-id="172bf-134">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="172bf-135">例如， https://test02-teamshealth.azurehealthcareapis.com/ 。</span><span class="sxs-lookup"><span data-stu-id="172bf-135">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 入口網站中中繼資料端點的螢幕擷取畫面](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="172bf-137">在 [團隊] 中，移至您團隊中載入的患者應用程式實例，按一下 [ **設定** ]，然後在 [ **連結** ] 方塊中輸入 FHIR 伺服器端點 URL。</span><span class="sxs-lookup"><span data-stu-id="172bf-137">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="172bf-138">接著，按一下 **[連線]** 以建立連線並搜尋，並將患者新增至您的清單。</span><span class="sxs-lookup"><span data-stu-id="172bf-138">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![團隊中的患者 app 設定的螢幕擷取畫面](../../media/patients-app-teams.png)
    
    <span data-ttu-id="172bf-140">如果您在執行此步驟時，在連線至團隊時收到錯誤，請傳送錯誤的詳細螢幕擷取畫面、 [Fiddler](https://www.telerik.com/download/fiddler) 的記錄，以及電子郵件中包含「患者 APP – EMR 模式疑難排解」主題行的任何其他重現步驟，以進行 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="172bf-140">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="172bf-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="172bf-141">Related topics</span></span>

- [<span data-ttu-id="172bf-142">病患應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="172bf-142">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="172bf-143">將電子醫療保健記錄整合至 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="172bf-143">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
