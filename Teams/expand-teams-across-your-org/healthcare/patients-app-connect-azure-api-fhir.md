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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>將病患應用程式連線至 Azure API for FHIR

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

請遵循下列步驟，允許 Microsoft Teams 中的病患應用程式存取 FHIR 實例的 Azure API。 本文假設您在租使用者中設定並設定 [了 FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 實例的 Azure API。  如果您尚未在租使用者中建立 FHIR 實例的 Azure API，請參閱快速入門：使用 Azure 入口網站部署[FHIR 的 Azure API。](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. 按一下 [這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 以授予病患應用程式的系統管理員同意。 當系統提示時，使用租使用者系統管理員或全域系統管理員認證來登錄，然後按一下 **[接受** 以授予必要的許可權。

    ![病患應用程式的許可權要求螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    接受之後，請關閉視窗。 您會看到看起來像這樣的頁面。 您可以忽略頁面上的錯誤訊息。 這是無害的，且表示已同意。  (我們正在為此 URL 建立一個更為使用者方便的頁面。 請留意！) 

    ![病患應用程式的許可權要求螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)

2. 使用系統管理員 [認證](https://portal.azure.com) 來登錄 Azure 入口網站。

3. 在左側流覽中，選取 **Azure Active Directory，** 然後選取 **企業應用程式**。

    尋找名為 **Patients** (dev) 列，然後將物件 **識別碼** 欄中的值複製到剪貼簿。

    ![Azure 入口網站中 (病患) 列的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)

4. 請前往您想要將病患應用程式連接到的 FHIR 資源實例的 Azure API (搜尋或流覽您的資源) ，然後開啟該實例的設定。

    ![Azure 入口網站 FHIR 實例設定 Azure API 的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. 按一下 **[驗證**，然後貼上您于步驟 3 中複製的物件識別碼至 [ **允許的物件識別碼>** 方塊。 這可讓病患應用程式存取 FHIR 伺服器。 貼上物件識別碼之後，Azure Active Directory 會驗證它，其旁邊會出現綠色核取方塊。

    ![Azure 入口網站驗證設定螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. 按一下 [儲存]。 這會重新部署實例，可能需要幾分鐘的時間。

7. 按一下 **[概** 觀，然後從 **FHIR 中繼資料端點複製 URL。** 移除元資料標記以取得 FHIR 伺服器 URL。 例如 `https://test02-teamshealth.azurehealthcareapis.com/` ，。

    ![Azure 入口網站中的中繼資料端點](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 在 Teams 中，前往小組中載入的病患應用程式實例，按一下 [設定>，然後在 [連結> 方塊中，輸入 FHIR 伺服器端點 URL。 接著，按一下 **[連接** 以建立連接並搜尋病患並新增到您的清單。  

    ![ Teams 中的病患應用程式設定](../../media/patients-app-teams.png)

    如果您在此步驟期間連接到 Teams 時發生錯誤，請傳送錯誤的詳細螢幕擷取畫面、[來自 Fiddler](https://www.telerik.com/download/fiddler)的記錄，以及電子郵件中任何其他回復步驟，其主題行為 「病患 App – EMR 模式疑難排解[」到 teamsforhealthcare@service.microsoft.com。](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>相關主題

- [病患應用程式概觀](patients-app-overview.md)
- [將電子醫療保健記錄整合至 Microsoft Teams](patients-app.md)