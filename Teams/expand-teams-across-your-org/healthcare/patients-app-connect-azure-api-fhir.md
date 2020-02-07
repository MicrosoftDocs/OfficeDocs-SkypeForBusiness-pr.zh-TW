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
description: 瞭解如何將 Microsoft 團隊中的患者 app 連線至 Azure API for FHIR （快速醫療保健互通性資源）。
ms.openlocfilehash: 92c5b033215b0e5520b0321042d52579dfb019bf
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827721"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>將病患應用程式連線至 Azure API for FHIR

請依照下列步驟，允許 Microsoft 團隊中的患者 app 存取 FHIR 實例的 Azure API。 本文假設您有在您的租使用者中設定和設定[FHIR 實例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。  如果您還沒有在租使用者中建立 FHIR 實例的 Azure API，請參閱[快速入門：使用 azure 入口網站部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。


1. 按一下[這裡](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806)以授與系統管理員同意的患者 app。 出現提示時，請使用您的租使用者管理員或全域系統管理員認證登入，然後按一下 [**接受**] 以授與所需的許可權。

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request.png)

    接受之後，請關閉視窗。 您會看到一個頁面，看起來會像這樣。 您可以忽略頁面上的錯誤訊息。 這不是無害的，指出已授與同意。 （我們正在處理更適合此 URL 的方便使用頁面。 保持及時調整！

    ![患者 App 許可權要求的螢幕擷取畫面](../../media/patients-app-permissions-request-granted.png)
2. 使用您的系統管理員認證登入[Azure 入口網站](https://portal.azure.com)。
3. 在左側導覽中，選取 [ **Azure Active Directory**]，然後選取 [**企業應用程式**]。
    尋找名為 **[患者（開發人員）**] 的列，然後將 [**物件識別碼**] 欄中的值複製到 [剪貼簿]。
    ![Azure 入口網站中的患者（開發人員）列的螢幕擷取畫面](../../media/patients-app-azure-portal-object-id.png)
4. 移至您想要將患者 app 連線至其中的 FHIR 資源實例的 Azure API （無論是透過搜尋或流覽您的資源），然後開啟該實例的設定。

    ![Azure API for Azure 入口網站中的 FHIR 實例設定的螢幕擷取畫面](../../media/patients-app-azure-portal-instance-settings.png)

5. 按一下 [**驗證**]，然後將您在步驟3中複製的物件識別碼貼到 [**允許的物件識別碼**] 方塊中。 這可讓患者 app 存取 FHIR 伺服器。 貼上物件識別碼之後，Azure Active Directory 會進行驗證，且旁邊會出現一個綠色的核取記號。

    ![Azure 入口網站驗證設定的螢幕擷取畫面](../../media/patients-app-azure-portal-authentication.png)

6. 按一下 [**儲存**]。 這會 redeploys 實例，可能需要幾分鐘的時間。
7. 按一下 **[概述**]，然後從**FHIR 中繼資料端點**複製 URL。 移除元資料標記以取得 FHIR 伺服器 URL。 例如， https://test02-teamshealth.azurehealthcareapis.com/。 

    ![Azure 入口網站中中繼資料端點的螢幕擷取畫面](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 在 [團隊] 中，移至您團隊中載入的患者應用程式實例，按一下 [**設定**]，然後在 [**連結**] 方塊中輸入 FHIR 伺服器端點 URL。 接著，按一下 **[連線]** 以建立連線並搜尋，並將患者新增至您的清單。  

    ![團隊中的患者 app 設定的螢幕擷取畫面](../../media/patients-app-teams.png)
    
    如果您在執行此步驟時，在連線至團隊時收到錯誤，請傳送錯誤的詳細螢幕擷取畫面、 [Fiddler](https://www.telerik.com/download/fiddler)的記錄，以及電子郵件中包含「患者 APP – EMR 模式疑難排解」主題行的任何其他重現步驟，以進行[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。

## <a name="related-topics"></a>相關主題

- [病患應用程式概觀](patients-app-overview.md)
- [將電子醫療保健記錄整合至 Microsoft Teams](patients-app.md)
