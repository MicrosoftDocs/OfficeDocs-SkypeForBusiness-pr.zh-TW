---
title: Microsoft 團隊中的安全性與合規性概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Microsoft 團隊安全性與合規性功能的概覽，包括審核與報告、相容性內容搜尋、eDiscovery 等。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f75d7fbbe3aa936163068e5652a6535d1b77251
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835833"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft 團隊中的安全性與合規性概述
======================================================

Microsoft 團隊是以 Office 365 超規模、企業級的雲端為基礎，提供客戶預期的高級安全性與合規性功能。

不要錯過這些關於安全性與合規性的 Microsoft 規範影片：
- [適用于 IT 的 Microsoft 團隊基本版：安全性與合規性](https://youtu.be/91lHNKVVvQ4)（12:42 分鐘）
- [Microsoft 團隊控制安全性與合規性](https://www.youtube.com/watch?v=Km4T4hMM__k)（10:54 分鐘）

團隊是標準的層級。 這包括下列標準： ISO 27001、ISO 27018、SSAE16 SOC 1 和 SOC 2、HIPAA 以及歐盟模型子句（EUMC）。 在 Microsoft 合規性架構中，Microsoft 將 Office 365 應用程式和服務分類成四種類別。 每個類別都是由要在該類別中列出的 Office 365 服務或相關 Microsoft 服務所需符合的特定合規性承諾所定義。

符合行業領先規範承諾的合規性類別 C 和 D 中的服務會預設為啟用。 [類別 A] 和 [B] 中的服務隨附控制項，可為整個組織開啟或關閉這些服務。 您可以在[規範架構中找到適用于行業標準與規章](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf)的詳細資料。 團隊也支援雲端安全聯盟規範。

團隊也會強制執行整個小組和組織範圍的雙因素驗證、透過 Active Directory 進行單一登入，以及在傳輸期間和存放的資料加密。 檔案是儲存在 SharePoint 中，且由 SharePoint 加密來支援。 筆記是儲存在 OneNote 中，且由 OneNote 加密所支援。 OneNote 資料會儲存在小組 SharePoint 網站。 [Wiki] 索引標籤也可用於記事記錄，而其內容也會儲存在小組 SharePoint 網站中。

我們也為頻道、聊天和檔案以及使用 Microsoft Intune 的行動應用程式管理，新增對審核記錄搜尋、eDiscovery 與法律封存的支援。 若要管理這些設定，請移至 Office 365 安全 & 合規性中心。 

若要深入瞭解 Office 365 的安全性和合規性，請閱讀[設定您的 Office 365 租使用者，以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前，[私有通道](private-channels.md)支援有限的安全性與合規性功能。 我們即將推出私人通道中完整的安全性與合規性功能的支援。

## <a name="auditing-and-reporting"></a>審核與報告

[審核記錄搜尋] 會直接移至 Office 365 安全性 & 合規性中心]，並在 [無限制的審核時程表] 中針對管理員使用及調查，公開設定警報與/或報告審核事件的功能。 所有的審核記錄資料都可在 Office 365 安全 & 合規性中心內設定通知，以及篩選和匯出以進行進一步分析。 請參閱此[連結](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)，深入瞭解如何在 Office 365 安全 & 合規性中心中執行 Microsoft 團隊活動的審核記錄搜尋。 

## <a name="compliance-content-search"></a>合規性內容搜尋

您可以使用內容搜尋，透過豐富的篩選功能搜尋所有團隊資料，並匯出至特定容器以進行合規性和訴訟支援。 您可以使用或不使用 eDiscovery 案例來完成此操作。 這可讓合規性系統管理員收集所有使用者的小組資料、審閱並匯出，以進行進一步的處理。 請參閱此[連結](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4)，深入瞭解如何在 Office 365 安全 & 合規性中心中進行 Microsoft 團隊內容搜尋。 

秘訣： Microsoft 團隊可以用來篩選僅限 Microsoft 團隊的內容，例如聊天與頻道訊息、會議和通話。

## <a name="ediscovery"></a>eDiscovery

電子查詢是識別、收集及出具電子儲存資訊（ESI）以回應法律或調查中的生產要求的電子方式。 功能包括案例管理、保留、搜尋、分析，以及匯出團隊資料。 這包括聊天、訊息與檔案、會議和通話摘要。 針對團隊會議和通話，在會議和通話中所發生事件的摘要會在 eDiscovery 中建立並提供。 

如需如何在安全性 & 合規性中心及執行合規性內容搜尋的詳細資料，請參閱下列連結： 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[內容搜尋](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

客戶可以根據自己的需求，利用就地 eDiscovery 或 [高級 eDiscovery] （https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)。 下表說明兩個專案之間的差異：


| |就地 eDiscovery  |高級 eDiscovery  |
|---------|---------|---------|
|案例管理     |X        |X         |
|存取控制  |X         |X         |
|內容搜尋     |X         | X        |
|按住（s）   |X         | X        |
|匯出     |X         |X         |
|重複偵測     |-         |X         |
|使用電腦學習進行關聯性搜尋    |-         |X         |
|非結構化資料分析      |-         |X         |


## <a name="legal-hold"></a>法律封存

在訴訟期間，通常需要與使用者（保管人）或團隊相關聯的所有資料都保留為不變，以便將它當作案例的證據使用。 您可以在法律封存中放置使用者（使用者信箱）或團隊來達到此目的。 當小組中的任何小組都放在已設定目標查詢或篩選內容的 [信箱] 或 [網站集合] 子集時（[整個信箱] 或 [網站集合]），[保留] 會放在 [群組] 信箱上。 這可確保即使最終使用者刪除或編輯 ingested 群組信箱中的頻道訊息，該內容的不可變複本仍會維持在 eDiscovery 搜尋中並提供。 法律封存一般會套用在 eDiscovery 案例的內容中。 請參閱[此](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a)說明文章，以深入瞭解如何在 Office 365 安全 & 合規性中心中保留和保留。 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Microsoft 團隊的資訊保護架構。 

下圖顯示小組檔案和郵件的 [從 Exchange 與 SharePoint 接收] 資料的攝取流程。 

![[小組] 資料至 Exchange 和 SharePoint 的工作流程圖表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下圖顯示團隊會議的攝取流程和呼叫資料至 Exchange。

![小組工作流程的圖表及呼叫資料至 Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 若要探索小組內容，最多可以有24小時的延遲時間。

<a name="licensing"></a>授權
---------------

當您遇到資訊保護功能時，Office 365 訂閱和相關聯的獨立授權將決定可用的功能集。


| 資訊保護功能 | Office 365 商務基本版 | Office 365 商務進階版 | Office 365 Enterprise E1 | Office 365 企業版 E3/E4 | Office 365 企業版 E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              壓縮              |               -                |              -              |            -             |             是             |           是            |
|        就地 eDiscovery        |               -                |              -              |            -             |             是             |           是            |
|        高級 eDiscovery        |               -                |              -              |            -             |              -              |           是            |
|            法律封存             |               -                |              -              |            -             |             是             |           是            |
|     合規性內容搜尋     |               -                |             是             |           是            |             是             |           是            |
|      審核與報告       |              是               |             是             |           是            |             是             |           是            |
|       條件式存取\*        |              是               |             是             |           是            |             是             |           是            |

> [!NOTE]
> \*條件式存取需要額外的授權


| |  |  |
|---------|---------|---------|
|![代表決策點的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |決策點         |貴組織是否有符合合規性與安全性商業需求的必要授權？         |
|![代表後續步驟的圖示](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |後續步驟         |查看貴組織目前的授權，並確認它符合合規性與安全性的所有業務需求。         |

在啟用任何這些功能之前，請先確定您有權存取 Microsoft 365 系統管理中心的安全性 & 合規性中心。 根據預設，租使用者管理員可以存取。

[內容搜尋] 和 [eDiscovery] 不需要在安全性 & 合規性中心中啟用。

<a name="location-of-data-in-teams"></a>Teams 中的資料位置
-------------------------

團隊中的資料位於與您的 Office 365 租使用者相關聯的地理區域中。 目前，團隊支援澳大利亞、加拿大、法國、印度、日本、英國、韓國、非洲、英國、韓國、南非、美洲、APAC 及 EMEA 地區。 

> [!IMPORTANT]
> 團隊目前在澳大利亞、加拿大、法國、印度、日本、英國、韓國、日本、英國、韓國，以及南非提供新租使用者的資料。 新的租使用者定義為任何沒有租使用者登入團隊中的使用者的租使用者。 澳大利亞、印度、日本和韓國的現有租使用者將繼續將其小組資料儲存在 APAC 區域中。 加拿大中的現有租使用者將繼續將其資料儲存在美洲。 在華北、英國和南非中，現有的租使用者將繼續將其資料儲存在 EMEA 地區。

在 Varun Sagar 的博客文章中，您可以在[Microsoft 團隊啟動南亞非洲資料派駐服務](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)中，在 [南部非洲] 資料的派駐者中找到更多相關資訊。

關於南亞朝鮮文資料的派駐者進一步閱讀 Varun Sagar 的博客文章， [Microsoft 團隊會啟動南亞韓文資料派駐](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)。

若要進一步瞭解如何啟動印度及英國資料的派駐者，請閱讀 Ansuman Acharya 的博客文章， [Microsoft 團隊會啟動印度資料派駐服務，即將推出其他 geos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)。 

如需有關適用于團隊的加拿大資料派駐服務的詳細資訊，請參閱 Varun Sagar 的博客文章，Microsoft 團隊會在即將推出[加拿大資料派駐、澳大利亞和日本](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)的情況下啟動。 

若要深入瞭解如何啟動澳大利亞和日本資料派駐服務，請參閱 Varun Sagar 的博客文章， [Microsoft 團隊會啟動澳大利亞和日本資料派駐服務](https://go.microsoft.com/fwlink/?linkid=867773)。 

若要進一步瞭解如何啟動針對團隊的法國資料派駐服務，請參閱 Varun Sagar 的博客文章， [Microsoft 團隊會啟動法國資料派駐](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)。

若要查看哪個地區駐留您租使用者的資料，請移至[Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) > **設定** > **組織設定檔**。 向下滾動至 [**資料位置**]。 

![資料位置資料表的螢幕擷取畫面，其中包含系統管理中心的團隊](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>條件式存取原則如何針對團隊運作？
-------------------------

Microsoft 團隊大量依賴 Exchange Online、SharePoint Online 和商務用 Skype Online 來取得核心生產力案例，例如會議、行事曆、交互操作聊天和檔案共用。 針對這些雲端應用程式設定的條件式存取原則，在使用者直接登入 Microsoft 團隊時（任何用戶端），都適用于 Microsoft 團隊。 

Microsoft 團隊獨立支援在 Azure Active Directory 條件式存取原則中作為雲端 app。 在使用者登入時，針對 Microsoft 團隊雲端 app 設定的條件式存取原則適用于 Microsoft 團隊。 不過，在其他 app （例如 Exchange Online 和 SharePoint Online）上沒有正確的原則，使用者仍然可以直接存取這些資源。 如需在 azure 入口網站中設定條件式存取原則的詳細資訊，請移至：（https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

適用于 Windows 和 Mac 的 Microsoft 團隊桌面用戶端支援新式驗證。 新式驗證會根據 Azure Active Directory 驗證程式庫（ADAL），在跨平臺的 Microsoft Office 用戶端應用程式中提供登入。

Microsoft 團隊桌面應用程式支援 AppLocker。  如需有關 AppLocker 必備元件的詳細資訊，請參閱：使用 AppLockerhttps://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)的需求（。

<a name="privacy-in-teams"></a>團隊中的隱私權
--------------------------

就像 Office 365 的客戶一樣，您擁有及控制您的資料。 除了向您提供已訂閱的服務之外，Microsoft 不會將您的資料用於任何其他專案。 身為服務提供者，我們不會掃描您的電子郵件、檔或團隊，以進行廣告或與服務相關的目的。 Microsoft 沒有已上傳內容的存取權。 就像商務用 OneDrive 和 SharePoint Online 一樣，客戶資料仍會留在租使用者中。

若要深入瞭解我們在[Microsoft 信任中心](https://microsoft.com/trustcenter)的信任與安全相關資訊，請參閱。 小組與 Microsoft 信任中心遵循相同的指導方針與原則。

<a name="related-topics"></a>相關主題
----------------------
[Office 365 ATP 安全連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
