---
title: Microsoft Teams 中的資料位置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，你將瞭解這些資料在 Microsoft Teams 中的地理位置。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121683"
---
# <a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams 中的資料位置

Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。 目前，Teams 支持澳大利亞、加拿大、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國、美洲、亞太地區和歐洲、中東和非洲地區。 

> [!IMPORTANT]
> Teams 目前只為新租用戶提供澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、韓國、南非和瑞士（包括列支敦斯登）的資料落地。
> 新的租用戶被定義為任何未從租用戶中的單個使用者登入 Teams 的租用戶。 來自澳大利亞、印度、日本和韓國的現有租戶將繼續將其 Teams 資料儲存在亞太地區。 加拿大的現有租用戶將繼續將其資料儲存在美國。 法國、德國、列支敦斯登、阿拉伯聯合大公國、英國、南非和瑞士的現有租戶的資料將儲存在歐洲、中東和非洲 (EMEA) 地區。

## <a name="where-your-teams-data-is-stored"></a>你的 Teams 資料的儲存位置

要查看哪些區域託管你的租用戶資料，請轉到 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) >  **[設置]** >  **[組織設定檔]**。 向下捲動到**資料位置**。

![包含系統管理中心中的 Teams 的資料位置表的螢幕截圖](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Teams 待用資料的位置

Teams 資料的儲存方式將有所不同，具體取決於內容類別型。 

![顯示 Teams 內容類別型及其待用儲存位置的圖表](media/location-of-data-storage-at-rest.png)

查看有關 [Microsoft Teams 結構的 Ignite 分組討論](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，以進行深入討論。

### <a name="core-teams-customer-data"></a>核心 Teams 客戶資料

如果您的租用戶位於澳大利亞、加拿大、歐盟、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國或美國，則 Microsoft 僅在該位置儲存以下客戶資料：

- Teams 聊天、小組和頻道交談、圖像、語音郵件和連絡人
- SharePoint Online 網站內容和儲存在該網站中的檔
- 上傳到商務用 OneDrive 的檔案

#### <a name="chat-channel-messages-team-structure"></a>聊天，頻道訊息，小組結構

Teams 中的每個小組都由 Microsoft 365 群組及其 SharePoint 網站和 Exchange 信箱支援。 私人聊天（包括群組聊天）、在頻道中作為交談一部分發送的訊息以及小組和頻道的結構都儲存在運行於 Azure 的聊天服務中。 資料還儲存在使用者和組信箱中的隱藏資料夾中，以啟用資訊保護功能。

#### <a name="voicemail-and-contacts"></a>語音郵件和連絡人

語音郵件儲存在 Exchange 中。 連絡人存儲在基於 Exchange 的雲端資料儲存區中。 Exchange 和基於 Exchange 的雲端儲存區已在全球每個資料中心地理位置提供資料落地。 對於所有小組，語音郵件和連絡人儲存在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國、瑞士（包括列支敦斯登）和美國的國家/地區。 對於所有其他國家/地區，基於租用戶相關性，檔案儲存在美國、歐洲或亞太地區。

#### <a name="images-and-media"></a>影像和媒體

聊天中使用的媒體 (Giphy GIF 除外，它沒有被儲存，但是指向原始 Giphy 服務 URL 的參考連結，Giphy 是非 Microsoft 服務) 儲存在基於 Azure 的媒體服務中，該服務部署到與聊天服務相同的位置。

#### <a name="files"></a>檔案

頻道中共用的檔案 (包括 OneNote 和 Wiki) 儲存在小組的 SharePoint 網站中。 在私人聊天、會議或通話期間的聊天中共用的檔將上載並儲存在 OneDrive 中，供共用該檔的使用者的商務帳戶使用。 Exchange、SharePoint 和 OneDrive 已經在全球每個資料中心地理位置提供資料落地。 因此，對於現有客戶，作為 Teams 體驗一部分的所有檔、OneNote 筆記本、Team wiki 內容和郵箱都已根據您的租用戶相關性儲存在該位置。 檔案存儲在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國和瑞士 (包括列支敦斯登) 的國家/地區。 對於所有其他國家/地區，基於租用戶相關性，檔案儲存在美國、歐洲或亞太地區。

### <a name="datacenter-locations"></a>資料中心位置

本節中描述的 Teams 服務將待用資料儲存在以下位置：

|國家或地區  |資料中心位置 |
|---------|---------|
|澳大利亞   |新南威爾士州和維多利亞         |
|加拿大    |魁北克市和多倫多         |
|法國    |馬賽和巴黎         |
|德國    |柏林和法蘭克福      |
|印度   |欽奈和浦那        |
|日本    |東京 (埼玉) 和大阪         |
|列支敦斯登   |日內瓦和蘇黎世       |
|南非     |約翰尼斯堡和開普敦         |
|韓國     |首爾和釜山         |
|瑞士    |日內瓦和蘇黎世       |
|阿拉伯聯合大公國     |阿布達比和杜拜         |
|英國     | 加的夫和倫敦        |
|美洲 - 北美洲和南美洲 (AMER) |加州灣和維珍尼亞州博伊頓       |
|亞太地區 (APAC)  |新加坡和香港特別行政區        |
|歐洲、中東和亞洲 (EMEA)   |都柏林和阿姆斯特丹        |

> [!NOTE]
> 對列支敦斯登來說，資料存儲在日內瓦和蘇黎世的瑞士資料中心。

### <a name="data-stored-with-a-third-party-storage-provider"></a>使用協力廠商儲存提供者儲存的資料

因此，對於那些依賴於協力廠商儲存位置的服務的使用者來說，應該允許他們將這些資料儲存在協力廠商的位置上。

- **索引標籤**：索引標籤可讓使用者將應用程式和服務中的資訊釘選到頻道。 因此，它因儲存資料的索引標籤類型而異。 該索引標籤本身不儲存任何資料。 例如，SharePoint 索引標籤將根據 SharePoint 網站集合的佈建位置儲存資料。 包含合作夥伴資訊的索引標籤將直接將資料儲存在合作夥伴使用的系統中，並且只顯示其檢視。
- **其他合作夥伴應用程式**：對於您可能在 Teams 體驗中使用的合作夥伴的應用程式和服務，Microsoft 不提供任何資料落地支援。 直接查看這些解決方案中的資訊，以瞭解其資料的儲存位置。

## <a name="see-also"></a>另請參閱

- [Microsoft Teams 推出阿拉伯聯合大公國資料落地](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams 推出韓國資料落地](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams 推出南非資料落地](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams 推出法國資料落地](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams 推出印度資料落地，即將推出其他地點](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams 推出澳大利亞和日本資料落地](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams 推出加拿大的資料落地、澳大利亞和日本即將推出](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
