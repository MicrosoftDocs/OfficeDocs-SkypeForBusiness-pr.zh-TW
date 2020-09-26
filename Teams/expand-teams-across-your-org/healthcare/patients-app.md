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
description: 瞭解如何使用 FHIR Api 將電子醫療保健記錄整合至 Microsoft 團隊患者 app。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1046037ff2cac7f98b9a34ede05a4b30ce793d6c
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277300"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>將電子醫療保健記錄整合至 Microsoft Teams

> [!IMPORTANT]
> **2020年9月30日生效，患者 app 將會被否決，且使用者將無法從 [小組] app store 進行安裝。我們鼓勵您立即開始使用團隊中的 [ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者 app 資料會儲存在可支援小組的 Office 365 群組群組信箱中。 當患者 app 停用時，所有與它相關聯的資料都會保留在這個群組中，但不能再透過使用者介面存取。 目前的使用者可以使用 [清單應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新建立其清單。
>
>[ [清單] 應用程式](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 是針對所有團隊使用者預先安裝的，而且在每個團隊和頻道中都可做為索引標籤。 透過清單，護理小組可以使用內建的患者範本、從頭開始，或是將資料匯入 Excel 來建立患者清單。 若要進一步瞭解如何管理組織中的 [清單] 應用程式，請參閱 [管理清單應用程式](../../manage-lists-app.md)。

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

本文適用于使用 FHIR Api 的一般醫療保健 IT 開發人員來連線至 Microsoft 團隊。 這會啟用符合醫療保健組織需求的護理協調案例。

連結的文章：針對 Microsoft 團隊患者應用程式的 FHIR 介面規格，以及下列各節說明在您的開發環境或租使用者中設定 FHIR 伺服器及連線患者 app 所需的內容。 您也需要熟悉已選取的 FHIR 伺服器檔，這必須是支援的其中一個選項：
- 透過其 [CMI](https://datica.com/compliant-managed-integration/) 提供的 Datica () 
- Infor Cloverleaf (透過 [INFOR FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)) 
- 透過 [R ^ FHIR 伺服器](https://www.redoxengine.com/fhir/) Redox () 
- Dapasoft (到 [COROLAR FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) 

> [!NOTE]
> 此程式不包括使用 Microsoft 團隊系統管理中心或 PowerShell Cmdlet 來啟用功能的步驟。 此設定會在 FHIR 伺服器/服務端和患者 app 用戶端中徹底完成。

以下所示是患者應用程式的架構：

![患者 app 架構的圖表](../../media/patients-app-architecture.png)

下列各節說明在 FHIR 伺服器 (或 EHR 啟用 FHIR) Api 的患者 app 中，僅限 FHIR 資料存取層級的需求，包括下列專案：

- 關於使用者驗證的預期
- 整合介面的功能和技術需求
- 效能與可靠性方面的期望
- 患者 app 支援的 FHIR 資源期望
- 整合程式與預期的接洽模型
- 如何開始使用 FHIR，以及患者 app 所面臨的一些常見挑戰
- 患者 app 下次反覆運算的未來需求

> [!NOTE]
> 在下列各節中，「合作夥伴」或「Interop 合作夥伴」一詞是用來參照任何協力廠商組織，可透過 FHIR 整合患者應用程式，並將 FHIR 伺服器與所列的規格搭配使用。

## <a name="functional-and-technical-requirements"></a>功能與技術需求  

### <a name="authentication"></a>驗證  

*不支援使用者層級授權*的 App 層級授權，就是執行資料轉換並公開連線來透過 FHIR 來 EHR 資料的最常見方式，即使 EHR 系統可能會執行使用者層級授權也一樣。 互通性服務 (的合作夥伴) 能提升對 EHR 資料的存取權，而且當它們公開與適當的 FHIR 資源相同的資料時，不會將授權內容傳遞到互通性服務消費者 (患者 app) 與互通性服務或平臺整合。 患者應用程式將無法強制執行使用者層級授權，但卻支援應用程式在患者 app 與互通性合作夥伴的服務之間進行應用程式驗證。

應用程式至應用程式驗證模型的描述如下：

應透過 OAuth 2.0 [用戶端認證流程](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)來執行服務驗證。 合作夥伴服務必須提供下列專案：

1. 合作夥伴服務可讓患者 app 建立合作夥伴的帳戶，這可讓患者 app 產生並擁有 client_id 和 client_secret，透過合作夥伴驗證服務器上的驗證登錄入口網站來管理。
2. 合作夥伴服務擁有驗證/授權系統，它會接受並驗證 (驗證) 提供的用戶端認證，並在範圍中傳回含租使用者認證的存取權杖，如下所述。
3. 出於安全考慮或在秘密破壞的情況下，患者應用程式可以重新產生機密，並無效或刪除舊的機密 (在 Azure 入口網站-AAD App 註冊) 中提供相同的範例。
4. 必須解除驗證託管一致性語句的中繼資料端點，才能無需驗證權杖。
5. 合作夥伴服務提供患者 app 的權杖端點，以使用用戶端認證流程來要求存取權杖。 每個授權伺服器的權杖 url，都應該是從 FHIR 伺服器上的中繼資料中取得的 FHIR 一致性 (功能) 語句，如下例所示：

* * *
    {"resourceType"： "CapabilityStatement"，。
        .
        .
        "rest"： [{] mode "：" server "，" security "： {" extension "： [{" extension "： [{" url "：] 權杖"，"valueUri"： " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token " "}，{" url "：" 授權 "，" valueUri "：" https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize ""} "，" url "：" "" ""，" http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris 服務"： [{"：" https://hl7.org/fhir/ValueSet/restful-security-service "" "Code"： "OAuth"} "" ""}，）。
                .
                .
            } ] }

* * *

存取權杖的要求包含下列參數：

* * *

    POST/token HTTP/1.1 主機： authorization-server.com

    grant 類型 = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx

* * *

合作夥伴服務提供患者 app 的 client_id 和 client_secret，透過合作夥伴端的驗證註冊入口網站加以管理。 合作夥伴服務提供端點以使用用戶端認證流程來要求存取權杖。 成功的回應必須包含 token_type、access_token 及 expires_in 參數。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>路由：將 AAD 租使用者對應至提供者端點

患者 app 會透過單一端點連接至合作夥伴服務。 合作夥伴服務擁有並維護一個機制，將每個 Microsoft 客戶 (AAD 租使用者識別碼) 對應到合作夥伴服務所使用的 FHIR 伺服器)  (的各個醫療保健提供者。

將 AAD 租使用者對應至提供者端點使用 AAD 租使用者識別碼 (GUID) 。 患者 app 會在範圍中傳遞租使用者識別碼，同時要求每個要求的存取權杖。 夥伴服務會保持租使用者識別碼與提供者端點的對應，並根據租使用者識別碼將要求重新導向至提供者端點。 若要這樣做，合作夥伴會在其端 (手動或透過入口網站上的設定，做為將提供者組織加入其互通性平臺) 的一部分。

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

雖然患者 app 是私人預覽，但並不保證端對端的效能。 效能中的因素包括工作流程中所涉及之所有躍點的相對延遲，從健康情況系統內容的 EHR 開始，到互通性合作夥伴及其基礎，包括 FHIR 伺服器以及跨 Office 365 生態系統和患者 app。

![互通性合作夥伴效能的圖例](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>開始使用 FHIR  

如果您是 FHIR 的新使用者，且需要輕鬆存取可公開給 Microsoft 團隊 EHR 整合介面的 FHIR 伺服器，Microsoft 有可供所有開發人員使用的開放來源 FHIR 伺服器。 請參閱 Azure 文章的 [FHIR 伺服器](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) ，以深入瞭解 Microsoft 提供的開放來源 FHIR 伺服器，並針對您的組織進行部署。

您也可以使用 HSPC Open 沙箱 EHR 環境來建立可支援開啟 FHIR 伺服器的 EHR，並使用這種方式來利用患者 app。 我們建議您閱讀 [HSPC 沙箱檔](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 沙箱不僅提供簡單且 UI 的功能，而且方便使用的建立、新增及編輯患者的方式，也提供了幾個開始使用的範例。 