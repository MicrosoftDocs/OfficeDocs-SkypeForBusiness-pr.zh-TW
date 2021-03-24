---
title: 病患應用程式概觀
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 瞭解如何使用 FHIR API 將電子醫療保健記錄整合至 Microsoft Teams 病患 App。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096207"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>將電子醫療保健記錄整合至 Microsoft Teams

> [!NOTE]
> 自 2020 年 10 月 30 日起，病患應用程式已淘汰並且由 Teams 中的[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)取代。 病患應用程式資料會儲存在支援小組之 Office 365 群組的群組信箱中。 所有與病患應用程式相關聯的資料會保留在此群組中，但是無法再透過使用者介面存取。 使用者可以使用[清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)來重新建立他們的清單。
>
>使用清單，您的醫療保健組織照護小組可以針對各種案例建立病患清單，範圍從會診和跨學科小組會議到一般病患監視。 請查看清單中的病患範本以開始使用。 若要深入了解如何在組織中管理清單應用程式，請參閱[管理清單應用程式](../../manage-lists-app.md)。

本文適用于一般醫療保健 IT 開發人員，有興趣使用醫療資訊系統頂端的 FHIR API 來連接到 Microsoft Teams。 這會啟用符合醫療保健組織需求的照護協調案例。

連結文章會記錄 Microsoft Teams Patients App 的 FHIR 介面規格，以下各節說明在開發環境或租使用者中設定 FHIR 伺服器並連接到病患應用程式所需的內容。 您也必須熟悉所選 FHIR 伺服器的檔，這必須是支援的其中一個選項：

- Datica ([透過 CMI](https://datica.com/compliant-managed-integration/) 方案) 
- Infor Cloverleaf ([Infor FHIR 橋接器) ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Redox ([R^FHIR 伺服器) ](https://www.redoxengine.com/fhir/)
- Dapasoft ([FHIR 上的 Corolar) ](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> 此程式不包含使用 Microsoft Teams 系統管理中心或 PowerShell Cmdlet 啟用功能的步驟。 此組組完全在 FHIR 伺服器/服務端和病患應用程式用戶端中完成。

以下說明的是病患應用程式的架構：

![病患應用程式架構圖表](../../media/patients-app-architecture.png)

下列各節說明 FHIR 伺服器 (或 EHR 啟用 FHIR API) 必須符合的病患應用程式 FHIR 僅 FHIR 資料存取層需求，包括下列各項：

- 使用者驗證的預期
- 整合介面的功能與技術需求
- 對績效和可靠性的預期
- 病患應用程式支援 FHIR 資源的預期
- 整合程式與預期的互動模型
- 如何開始使用 FHIR，以及病患應用程式所面臨的一些常見挑戰
- 病患應用程式下一次反覆運算的未來需求

> [!NOTE]
> 在下列各節中，「合作夥伴」或「Interop 合作夥伴」一詞會用來指任何協力廠商組織，該協力廠商組織能透過 FHIR 整合至病患應用程式的 EHR 系統，並且正在實施符合所列規格的 FHIR Server。

## <a name="functional-and-technical-requirements"></a>功能與技術需求  

### <a name="authentication"></a>驗證  

不支援使用者層級授權的App 層級授權是執行資料轉換，並透過 FHIR 公開 EHR 資料連結的常見方式，即使 EHR 系統可能實行使用者層級授權。 Interop Service (合作夥伴) 會提升 EHR 資料的存取權，且當對方公開與適當的 FHIR 資源相同的資料時，不會將授權上下文傳遞至 Interop 服務消費者 (病患應用程式) 整合至 Interop 服務或平臺。 病患應用程式無法強制執行使用者層級授權，但支援應用程式以在病患 App 與 Interop 合作夥伴的服務之間執行應用程式驗證。

以下說明應用程式到應用程式驗證模型：

服務到服務驗證應該透過 OAuth 2.0 [用戶端認證流程完成](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 合作夥伴服務必須提供下列專案：

1. 合作夥伴服務可讓病患應用程式與合作夥伴建立帳戶，讓病患應用程式產生及擁有 client_id 和 client_secret，透過合作夥伴的驗證服務器的驗證註冊入口網站管理。

2. 合作夥伴服務擁有驗證/授權系統，系統接受並驗證 (驗證) 所提供的用戶端認證，並且提供具有租使用者提示的存取權杖，如下所示。

3. 基於安全性考慮，或發生秘密入侵的情況，在 Azure 入口網站 - AAD 應用程式註冊) 中，病患應用程式可以重新產生機密，並失效或刪除舊密碼 (範例。

4. 託管一致性語句的中繼資料端點應該未經驗證，而且應該無需驗證權杖即可使用。

5. 合作夥伴服務提供權杖端點，讓病患應用程式使用用戶端認證流程要求存取權杖。 每個授權伺服器的權杖 URL 應屬於 FHIR 一致性 (功能) 從 FHIR 伺服器上從中繼資料提取的語句，如此範例所示：

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

存取權杖要求包含下列參數：

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

合作夥伴服務透過合作夥伴client_id client_secret驗證註冊入口網站管理，提供病患應用程式的應用程式與服務。 合作夥伴服務提供端點，以使用用戶端認證流程要求存取權杖。 成功的回應必須包含token_type、access_token expires_in參數。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>路由：將 AAD 租使用者與提供者端點進行映射

病患應用程式會透過單一端點連接到合作夥伴服務。 合作夥伴服務擁有並維護一個機制，將每個 Microsoft 客戶 (AAD 租使用者識別碼) 與合作夥伴服務正在處理之各自的醫療保健提供者 (FHIR 伺服器) 進行地圖處理。

將 AAD 租使用者與提供者端點的映射使用 AAD 租使用者識別碼 (GUID) 。 病患應用程式會以範圍傳遞租使用者識別碼，同時針對每個要求要求存取權杖。 合作夥伴服務會保留租使用者識別碼與提供者端點的映射，並依據租使用者識別碼將要求重新導向到提供者端點。 若要這麼做，合作夥伴會手動或透過入口網站 (端支援組) 。

驗證和路由工作流程如下所示：

![驗證和路由工作流程圖表](../../media/Patient-app-6.png)

1. 傳送應用程式存取權杖要求：
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. 使用應用程式權杖回復：

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. 使用 Access 權杖要求受保護的資料。

4. 授權訊息：選取適當的 FHIR 伺服器，以在範圍中從租使用者識別碼路由至。

5. 使用應用程式權杖驗證之後，從授權 FHIR 伺服器傳送應用程式受保護的資料。

## <a name="interfaces"></a>介面

下列文章會記錄病患應用程式使用的特定通話和欄位。 選取適用于 FHIR 伺服器/FHIR API 的介面。

- [DSTU2 介面規格](dstu2-interface.md)
- [STU3 介面規格](stu3-interface.md)

## <a name="performance-and-reliability"></a>績效與可靠性

雖然病患應用程式是私人預覽版，但端對端效果並沒有任何保證。 影響績效的因素包括工作流程中所有躍點的相對延遲，從健康系統內容中 EHR 開始，到 Interop 合作夥伴及其內部活動 ，包括 FHIR Server，以及 Office 365 生態系統和病患應用程式。

![Interop 合作夥伴績效圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>開始使用 FHIR  

如果您是 FHIR 的新使用者，而且需要輕鬆存取 FHIR Server，且該伺服器可以公開至 Microsoft Teams EHR 整合介面，Microsoft 擁有開放來源 FHIR 伺服器，可供所有開發人員使用。 請參閱什麼是 [Azure FHIR Server](/azure/healthcare-apis/overview-open-source-server) 一文，以深入瞭解 Microsoft 提供的開放來源 FHIR Server，並針對組織進行部署。

您也可以使用 HSPC Open 沙箱 EHR 環境來建立 EHR，該 EHR 也支援開啟的 FHIR Server，並使用它與病患應用程式一起玩。 我們建議您閱讀 [HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 沙箱不僅提供簡單且 UI 導向且使用者易於建立、新增和編輯病患的方式，同時也提供數個範例讓您開始使用。