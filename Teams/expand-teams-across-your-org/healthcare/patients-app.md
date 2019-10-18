---
title: 患者 app 概述
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 團隊患者 app EHR 整合
ms.openlocfilehash: d3869d8646a417ec681a48321610b7cfffd50e5a
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569287"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>將電子醫療保健記錄整合至 Microsoft 團隊

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

若要參與私人預覽版，請參閱[註冊私人預覽](#enroll-in-the-private-preview)。

本文適用于使用 FHIR Api 的一般醫療保健 IT 開發人員來連線至 Microsoft 團隊。 這會啟用符合醫療保健組織需求的護理協調案例。

連結的文章：針對 Microsoft 團隊患者應用程式的 FHIR 介面規格，以及下列各節說明在您的開發環境或租使用者中設定 FHIR 伺服器及連線患者 app 所需的內容。 您也需要熟悉已選取的 FHIR 伺服器檔，這必須是支援的其中一個選項：
- Datica （透過其[CMI](https://datica.com/compliant-managed-integration/)產品）
- Infor Cloverleaf （透過[INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)）
- Redox （透過[R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/)）
- Dapasoft （透過[Corolar 上的 FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)）

> [!NOTE]
> 此程式不包括使用 Microsoft 團隊系統管理中心或 PowerShell Cmdlet 來啟用功能的步驟。 此設定會在 FHIR 伺服器/服務端和患者 app 用戶端中徹底完成。

以下所示是患者應用程式的架構：

![患者 app 架構的圖表](../../media/patients-app-architecture.png)

下列各節說明適用于 FHIR 伺服器（或 EHR 支援的 FHIR Api）的 FHIR 資料存取層級的需求，以便與患者 app 整合，包括下列各項：

- 關於使用者驗證的預期
- 整合介面的功能和技術需求
- 效能與可靠性方面的期望
- 患者 app 支援的 FHIR 資源期望
- 整合程式與預期的接洽模型
- 如何在患者 app 的私人預覽版中自行註冊您的客戶
- 如何開始使用 FHIR，以及患者 app 所面臨的一些常見挑戰
- 患者 app 下次反覆運算的未來需求

> [!NOTE]
> 在下列各節中，「合作夥伴」或「Interop 合作夥伴」一詞是用來參照任何協力廠商組織，可透過 FHIR 整合患者應用程式，並將 FHIR 伺服器與所列的規格搭配使用。

## <a name="functional-and-technical-requirements"></a>功能與技術需求  

### <a name="authentication"></a>Authentication  

*不支援使用者層級授權*的 App 層級授權是更常受支援的資料轉換方式，也是透過 FHIR 公開連線來 EHR 資料，即使 EHR 系統可能會執行使用者層級授權. 互通性服務（合作夥伴）會取得 EHR 資料的提升存取權，當其公開與適當的 FHIR 資源相同的資料時，不會將授權內容傳到互通性服務消費者（患者 app）與互通性整合[服務] 或 [平臺]。 患者應用程式將無法強制執行使用者層級授權，但卻支援應用程式在患者 app 與互通性合作夥伴的服務之間進行應用程式驗證。

應用程式至應用程式驗證模型的描述如下：

應透過 OAuth 2.0[用戶端認證流程](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)來執行服務驗證。 合作夥伴服務必須提供下列專案：

1. 合作夥伴服務可讓患者 app 建立合作夥伴的帳戶，這可讓患者 app 產生並擁有 client_id 和 client_secret，透過合作夥伴驗證服務器上的驗證登錄入口網站來管理。
2. 合作夥伴服務擁有驗證/授權系統，可接受並驗證（驗證）提供的用戶端認證，並在範圍中傳回含租使用者的存取權杖，如下所述。
3. 出於安全考慮或在秘密破壞的情況下，患者應用程式可以重新產生密碼，並使或刪除舊的密碼（例如，Azure 入口網站-AAD App 註冊中提供相同的範例）
4. 必須解除驗證託管一致性語句的中繼資料端點，才能無需驗證權杖。
5. 合作夥伴服務提供患者 app 的權杖端點，以使用用戶端認證流程來要求存取權杖。 每個授權伺服器的權杖 url，都應該是從 FHIR 伺服器上的中繼資料中取得的 FHIR 規範（功能）語句的一部分，如下例所示：

* * *
    {"resourceType"： "CapabilityStatement"，。
        .
        .
        "rest"： [{] mode "：" server "，" security "： {" extension "： [{" extension "： [{] url"： "" token "，" valueUri "：https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" ""}，{"url"： "授權"，"valueUri"https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize： ""}]，"url"http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris： "" ""： [{"system"： "http://hl7.org/fhir/ValueSet/restful-security-service" "" ""： "OAuth"} ] } ] }, .
                .
                .
            } ] }

* * *

存取權杖的要求包含下列參數：

* * *

    POST/token HTTP/1.1 主機： authorization-server.com

    grant 類型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx

* * *

合作夥伴服務提供患者 app 的 client_id 和 client_secret，透過合作夥伴端的驗證註冊入口網站加以管理。 合作夥伴服務提供端點以使用用戶端認證流程來要求存取權杖。 成功的回應必須包含 token_type、access_token 和 expires_in 參數。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>路由：將 AAD 租使用者對應至提供者端點

患者 app 會透過單一端點連接至合作夥伴服務。 合作夥伴服務擁有及維護將每個 Microsoft 客戶（AAD 租使用者識別碼）對應給合作夥伴服務所使用的各個醫療保健提供者（FHIR 伺服器）的機制。

將 AAD 租使用者對應至提供者端點會使用 AAD 租使用者識別碼（GUID）。 患者 app 會在範圍中傳遞租使用者識別碼，同時要求每個要求的存取權杖。 夥伴服務會保持租使用者識別碼與提供者端點的對應，並根據租使用者識別碼將要求重新導向至提供者端點。 若要這樣做，合作夥伴就能在其端（無論是提供給提供者組織的互通性平臺）中，以手動或透過入口網站的方式來支援設定。

驗證與路由工作流程如下所示：

![驗證與路由工作流程的圖表](../../media/Patient-app-6.png)

1. 傳送應用程式存取權杖的要求：
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. 使用應用程式權杖回復：

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. 使用存取權杖要求受保護的資料。
4. 授權訊息：選取要從作用中的租使用者識別碼路由至適當的 FHIR 伺服器
5. 在驗證應用程式權杖之後，從授權的 FHIR 伺服器傳送受保護的資料。

## <a name="interfaces"></a>交互

下列文章中記錄患者 app 所使用的特定通話和欄位。 選取適用于您的 FHIR server/FHIR Api 的介面。

- [DSTU2 介面規格](dstu2-interface.md)
- [STU3 介面規格](stu3-interface.md)

## <a name="performance-and-reliability"></a>效能與可靠性

雖然患者 app 是私人預覽，但並不保證端對端的效能。 效能中的因素包括工作流程中所涉及之所有躍點的相對延遲，從健康情況系統內容的 EHR 開始，到互通性合作夥伴及其基礎，包括 FHIR 伺服器以及在 Office 365 生態系統中。患者 app。

![互通性合作夥伴效能的圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>開始使用 FHIR  

如果您是 FHIR 的新使用者，且需要輕鬆存取可公開給 Microsoft 團隊 EHR 整合介面的 FHIR 伺服器，Microsoft 有可供所有開發人員使用的開放來源 FHIR 伺服器。 請參閱 Azure 文章的[FHIR 伺服器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)，以深入瞭解 Microsoft 提供的開放來源 FHIR 伺服器，並針對您的組織進行部署。

您也可以使用 HSPC Open 沙箱 EHR 環境來建立可支援開啟 FHIR 伺服器的 EHR，並使用這種方式來利用患者 app。 我們建議您閱讀[HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 沙箱不僅提供簡單且 UI 的功能，而且方便使用的建立、新增及編輯患者的方式，也提供了幾個開始使用的範例。  

## <a name="enroll-in-the-private-preview"></a>註冊私人預覽

在您建立開放來源 FHIR 伺服器之後，請遵循下列步驟，在您的租使用者內連線至患者 app 是相當簡單的做法：

1. [請](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)與下列初始詳細資料與我們聯繫：  
    - 您的姓名
    - 您的位置
    - 您所代表的公司或組織
    - 為什麼您對 EHR 整合感興趣

    我們會儘快取得您的相關問題，並引導您完成設定私人預覽版的程式。

2. 請確定您要用來嘗試患者 app 的租使用者已啟用自訂應用程式的側載。 請參閱[應用程式許可權原則](../../admin-settings.md)，以瞭解如何從適用于您或客戶租使用者的小組系統管理中心開啟此操作。

3. 側載您將從 Microsoft 取得的患者 app 資訊清單（在我們將您的電子郵件處理至我們之後），移至租使用者用來進行護理與患者化整案例的小組中。 關於如何側載應用程式的詳細指示，請參閱將[應用程式套件上傳到 Microsoft 團隊](/microsoftteams/platform/concepts/apps/apps-upload)

4. 流覽至 [一般] 頻道作為小組擁有者，然後按一下 [患者] 索引標籤。您應該會看到第一個執行體驗，其中會出現兩個選項，例如 EHR 模式和手動模式。 請選取**EHR 模式**，然後複製 FHIR 伺服器端點（您已將上述所需的所有必要資料和資源安裝在 Link 功能變數中，並為連線提供良好的名稱來代表 FHIR 伺服器）。 按一下 [連線]，一切就應該準備就緒即可開始。

    ![患者 app 伺服器設定的螢幕擷取畫面](../../media/patients-server.png)

5. 開始使用 app 從 FHIR Server/EHR 搜尋患者，並將它們新增到清單中，並在問題無法使用時[提供意見反應給我們](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)。 此外，若要建立完整的驗證版本的患者 app-> FHIR 伺服器流程，請透過舊版的 Microsoft 團隊進行醫療保健產品工程，並在前面提到的電子郵件要求來闡明需求，我們將根據上述 FHIR 介面檔中所述的驗證需求，協助為您啟用此功能。  


