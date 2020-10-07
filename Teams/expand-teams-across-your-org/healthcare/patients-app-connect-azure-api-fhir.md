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
ms.openlocfilehash: 3bd6cdc694eb197c1e8fd45d7e133576732cdc22
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367613"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>將病患應用程式連線至 Azure API for FHIR

> [!IMPORTANT]
> **2020年10月30日生效，患者應用程式將會被否決，且使用者將無法從 [小組 app store] 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。 當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。 目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。
>
>[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。 透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

請依照下列步驟，允許 Microsoft 團隊中的患者 app 存取 FHIR 實例的 Azure API。 本文假設您有在您的租使用者中設定和設定 [FHIR 實例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。  如果您還沒有在租使用者中建立 FHIR 實例的 Azure API，請參閱 [快速入門：使用 azure 入口網站部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。


1. 按一下 [這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 以授與系統管理員同意的患者 app。 出現提示時，請使用您的租使用者管理員或全域系統管理員認證登入，然後按一下 [ **接受** ] 以授與所需的許可權。

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    接受之後，請關閉視窗。 您會看到一個頁面，看起來會像這樣。 您可以忽略頁面上的錯誤訊息。 這不是無害的，指出已授與同意。  (我們正在處理更適合此 URL 的方便使用頁面。 掌握最新資訊！ ) 

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)
2. 使用您的系統管理員認證登入 [Azure 入口網站](https://portal.azure.com) 。
3. 在左側導覽中，選取 [ **Azure Active Directory**]，然後選取 [ **企業應用程式**]。
    尋找名為 [ **患者 (dev) **的列，然後將 [ **物件識別碼** ] 欄中的值複製到 [剪貼簿]。
    ![Azure 入口網站) 資料列的患者 (開發人員的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)
4. 若要將患者 (app 連線至 FHIR 資源實例的 Azure API，請進行搜尋，或流覽您的資源) ，然後開啟該實例的設定。

    ![Azure API for Azure 入口網站中的 FHIR 實例設定的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. 按一下 [ **驗證**]，然後將您在步驟3中複製的物件識別碼貼到 [ **允許的物件識別碼** ] 方塊中。 這可讓患者 app 存取 FHIR 伺服器。 貼上物件識別碼之後，Azure Active Directory 會進行驗證，且旁邊會出現一個綠色的核取記號。

    ![Azure 入口網站驗證設定的螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. 按一下 [儲存]****。 這會 redeploys 實例，可能需要幾分鐘的時間。
7. 按一下 **[概述**]，然後從 **FHIR 中繼資料端點**複製 URL。 移除元資料標記以取得 FHIR 伺服器 URL。 例如， https://test02-teamshealth.azurehealthcareapis.com/ 。 

    ![Azure 入口網站中中繼資料端點的螢幕擷取畫面](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 在 [團隊] 中，移至您團隊中載入的患者應用程式實例，按一下 [ **設定**]，然後在 [ **連結** ] 方塊中輸入 FHIR 伺服器端點 URL。 接著，按一下 **[連線]** 以建立連線並搜尋，並將患者新增至您的清單。  

    ![團隊中的患者 app 設定的螢幕擷取畫面](../../media/patients-app-teams.png)
    
    如果您在執行此步驟時，在連線至團隊時收到錯誤，請傳送錯誤的詳細螢幕擷取畫面、 [Fiddler](https://www.telerik.com/download/fiddler) 的記錄，以及電子郵件中包含「患者 APP – EMR 模式疑難排解」主題行的任何其他重現步驟，以進行 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。

## <a name="related-topics"></a>相關主題

- [病患應用程式概觀](patients-app-overview.md)
- [將電子醫療保健記錄整合至 Microsoft Teams](patients-app.md)
